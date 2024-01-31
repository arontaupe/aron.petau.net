---
title:  "AIRASPI Build Log"
author: "Aron Petau"
excerpt: "Utilizing an edge TPU to build an edge device for image recognition and object detection"
tags:
  - local AI
  - coral
  - raspberry pi
  - edge TPU
  - docker
  - frigate
  - private
  - surveillance
---

## airaspi build log

This should document the rough steps to recreate airaspi as i go along.

Rough idea: Build an edge device with image recognitionm and object detection capabilites.
It should be realtime, aiming for 30fps at 720p.
Inspo from: [pose2art](https://github.com/MauiJerry/Pose2Art)

work in progress
{: .notice}

## Hardware

- [Raspberry Pi 5](https://www.raspberrypi.com/products/raspberry-pi-5/)
- [Raspberry Pi Camera Module v1.3](https://www.raspberrypi.com/documentation/accessories/camera.html)
- [Raspberry Pi GlobalShutter Camera](https://www.raspberrypi.com/documentation/accessories/camera.html)
- 2x CSI FPC Cable (needs one compact side to fit pi 5)
- [Pineberry AI Hat (m.2 E key)](https://pineberrypi.com/products/hat-ai-for-raspberry-pi-5)
- [Coral Dual Edge TPU (m.2 E key)](https://www.coral.ai/products/m2-accelerator-dual-edgetpu)
- Raspi Official 5A Power Supply
- Raspi active cooler

## Setup

### Most important sources used

[coral.ai](https://www.coral.ai/docs/m2/get-started/#requirements)
[Jeff Geerling](https://www.jeffgeerling.com/blog/2023/pcie-coral-tpu-finally-works-on-raspberry-pi-5)
[Frigate NVR](https://docs.frigate.video)

### Raspberry Pi OS

I used the Raspberry Pi Imager to flash the latest Raspberry Pi OS Lite to a SD Card.

Needs to be Bookworm
Needs to be the full arm64 image (with desktop), otherwise you will get into camera driver hell
{: .notice}

Settings applied:

-- used the default arm64 image (with desktop)
-- enable custom settings:
-- enable ssh
-- set wifi country
-- set wifi ssid and password
-- set locale
-- set hostname: airaspi

### update

always good practice on a fresh install. takes quite long with the full os image

```zsh
sudo apt update && sudo apt upgrade -y && sudo reboot
```

### prep system for coral

Thanks again @Jeff Geerling, this is completely out of my comfort zone, I rely on people writing solid tutorials like this one.

```zsh
# check kernel version
uname -a
```

```zsh
# modify config.txt
sudo nano /boot/firmware/config.txt
```

while in the file, add the following lines:
  
```config
kernel=kernel8.img
dtparam=pciex1
dtparam=pciex1_gen=2
```

save and reboot

```zsh
sudo reboot
```

```zsh
# check kernel version again
uname -a
```

-- should be different now, with a -v8 at the end

edit /boot/firmware/cmdline.txt

```zsh
sudo nano /boot/firmware/cmdline.txt
```

-- add pcie_aspm=off before rootwait

```zsh
sudo reboot
```

### change device tree

#### wrong device tree

maybe this script is the issue?
i will try again without it
{: .notice}

```zsh
curl https://gist.githubusercontent.com/dataslayermedia/714ec5a9601249d9ee754919dea49c7e/raw/32d21f73bd1ebb33854c2b059e94abe7767c3d7e/coral-ai-pcie-edge-tpu-raspberrypi-5-setup | sh
```

-- yes it was the issue, wrote a comment about it on the gist
[comment](https://gist.github.com/dataslayermedia/714ec5a9601249d9ee754919dea49c7e?permalink_comment_id=4860232#gistcomment-4860232)

What to do instead?

here, I followed Jeff geerling down to the t. please refer to his tutorial for more information.

```zsh
# Back up the current dtb
sudo cp /boot/firmware/bcm2712-rpi-5-b.dtb /boot/firmware/bcm2712-rpi-5-b.dtb.bak

# Decompile the current dtb (ignore warnings)
dtc -I dtb -O dts /boot/firmware/bcm2712-rpi-5-b.dtb -o ~/test.dts

# Edit the file
nano ~/test.dts

# Change the line: msi-parent = <0x2f>; (under `pcie@110000`)
# To: msi-parent = <0x66>;
# Then save the file.

# Recompile the dtb and move it back to the firmware directory
dtc -I dts -O dtb ~/test.dts -o ~/test.dtb
sudo mv ~/test.dtb /boot/firmware/bcm2712-rpi-5-b.dtb
```

Note: msi- parent sems to carry the value <0x2c> nowadays, cost me a few hours.
{: .notice}

### install apex driver

following instructions from [coral.ai](https://coral.ai/docs/m2/get-started#2a-on-linux)

```zsh
echo "deb https://packages.cloud.google.com/apt coral-edgetpu-stable main" | sudo tee /etc/apt/sources.list.d/coral-edgetpu.list

curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add -

sudo apt-get update

sudo apt-get install gasket-dkms libedgetpu1-std

sudo sh -c "echo 'SUBSYSTEM==\"apex\", MODE=\"0660\", GROUP=\"apex\"' >> /etc/udev/rules.d/65-apex.rules"

sudo groupadd apex

sudo adduser $USER apex
```

verify with

```zsh
lspci -nn | grep 089a
```

-- should display the connected tpu

```zsh
sudo reboot
```

confirm with, if the output is not /dev/apex_0, something went wrong

```zsh
ls /dev/apex_0
```

### Docker

install docker, use official instructions for debian

```zsh
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

```zsh
#add user to docker group
sudo groupadd docker
sudo usermod -aG docker $USER
```

probably, a source with source .bashrc would be enough, but i rebooted anyways
{: .notice}

```zsh
sudo reboot
```

```zsh
# verify with
docker run hello-world
```

# set docker to start on boot

```zsh
sudo systemctl enable docker.service
sudo systemctl enable containerd.service
```

### test the edge tpu

```zsh
mkdir coraltest
cd coraltest
sudo nano Dockerfile
```

into the new file,paste:

```Dockerfile
FROM debian:10

WORKDIR /home
ENV HOME /home
RUN cd ~
RUN apt-get update
RUN apt-get install -y git nano python3-pip python-dev pkg-config wget usbutils curl

RUN echo "deb https://packages.cloud.google.com/apt coral-edgetpu-stable main" \
| tee /etc/apt/sources.list.d/coral-edgetpu.list
RUN curl https://packages.cloud.google.com/apt/doc/apt-key.gpg | apt-key add -
RUN apt-get update
RUN apt-get install -y edgetpu-examples
```

```zsh
# build the docker container
docker build -t "coral" .
```

```zsh
# run the docker container
docker run -it --device /dev/apex_0:/dev/apex_0 coral /bin/bash
```

```zsh
# run an inference example from within the container
python3 /usr/share/edgetpu/examples/classify_image.py --model /usr/share/edgetpu/examples/models/mobilenet_v2_1.0_224_inat_bird_quant_edgetpu.tflite --label /usr/share/edgetpu/examples/models/inat_bird_labels.txt --image /usr/share/edgetpu/examples/images/bird.bmp
```

here, you should see the inference results from the edge tpu with some confidence values.
if it aint so, safest bet is a clean restart

### Portainer

optional, gives you a browser gui for your various docker containers
{: .notice}

install portainer

```zsh
docker volume create portainer_data
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```

open portainer in browser and set admin password
-- should be available under <https://airaspi.local:9443>

### vnc in raspi-config

optional, useful to test your cameras on your headless device.
You could of course also attach a monitor, but i find this more convenient.
{: .notice}

```zsh
sudo raspi-config
```

-- interface otions, enable vnc

### connect through vnc viewer

install vnc viewer on mac
use airaspi.local:5900 as address

### working docker-compose for frigate

start this as a custom template in portainer

Imoportant: you need to change the paths to your own paths
{: .notice}

```yaml
version: "3.9"
services:
  frigate:
    container_name: frigate
    privileged: true # this may not be necessary for all setups
    restart: unless-stopped
    image: ghcr.io/blakeblackshear/frigate:stable
    shm_size: "64mb" # update for your cameras based on calculation above
    devices:
      - /dev/apex_0:/dev/apex_0 # passes a PCIe Coral, follow driver instructions here https://coral.ai/docs/m2/get-started/#2a-on-linux

    volumes:
      - /etc/localtime:/etc/localtime:ro
      - /home/aron/frigate/config.yml:/config/config.yml # replace with your config file
      - /home/aron/frigate/storage:/media/frigate # replace with your storage directory
      - type: tmpfs # Optional: 1GB of memory, reduces SSD/SD Card wear
        target: /tmp/cache
        tmpfs:
          size: 1000000000
    ports:
      - "5000:5000"
      - "8554:8554" # RTSP feeds
      - "8555:8555/tcp" # WebRTC over tcp
      - "8555:8555/udp" # WebRTC over udp
    environment:
      FRIGATE_RTSP_PASSWORD: "******"
```

### working frigate config file

frigate wants this file wherever you specified earlier that it will be.
this is necessary just once. Afterwards, you will be able to change the config in the gui.
{: .notice}

```yaml
mqtt:
  enabled: False

detectors:
  cpu1:
    type: cpu
    num_threads: 3
  coral_pci:
    type: edgetpu
    device: pci

cameras:
  cam1: # <------ Name the camera
    ffmpeg:
      hwaccel_args: preset-rpi-64-h264
      inputs:
        - path: rtsp://192.168.1.58:8900/cam1
          roles:
            - detect
  cam2: # <------ Name the camera
    ffmpeg:
      hwaccel_args: preset-rpi-64-h264
      inputs:
        - path: rtsp://192.168.1.58:8900/cam2
          roles:
            - detect
    detect:
      enabled: True # <---- disable detection until you have a working camera feed
      width: 1280 # <---- update for your camera's resolution
      height: 720 # <---- update for your camera's resolution
```

### mediamtx

install mediamtx, do not use the docker version, it will be painful

double check the chip architecture here, caused me some headache
{: .notice}

```zsh
mkdir mediamtx
cd mediamtx
wget https://github.com/bluenviron/mediamtx/releases/download/v1.5.0/mediamtx_v1.5.0_linux_arm64v8.tar.gz

tar xzvf mediamtx_v1.5.0_linux_arm64v8.tar.gz && rm mediamtx_v1.5.0_linux_arm64v8.tar.gz
```

edit the mediamtx.yml file

### working paths section in mediamtx.yml

```yaml
paths:
 cam1:
   runOnInit: bash -c 'rpicam-vid -t 0 --camera 0 --nopreview --codec yuv420 --width 1280 --height 720 --inline --listen -o - | ffmpeg -f rawvideo -pix_fmt yuv420p -s:v 1280x720 -i /dev/stdin -c:v libx264 -preset ultrafast -tune zerolatency -f rtsp rtsp://localhost:$RTSP_PORT/$MTX_PATH'
   runOnInitRestart: yes
 cam2:
   runOnInit: bash -c 'rpicam-vid -t 0 --camera 1 --nopreview --codec yuv420 --width 1280 --height 720 --inline --listen -o - | ffmpeg -f rawvideo -pix_fmt yuv420p -s:v 1280x720 -i /dev/stdin -c:v libx264 -preset ultrafast -tune zerolatency -f rtsp rtsp://localhost:$RTSP_PORT/$MTX_PATH'
   runOnInitRestart: yes
```

also change rtspAddress: :8554 --to-- rtspAddress: :8900
 otherwise there is a conflict with frigate

with this, you should be able to start mediamtx

```zsh
./mediamtx
```

if there is no error, you can verify your stream through vlc under rtsp://airaspi.local:8900/cam1 (default would be 8554, but we changed it in the config file)

### Current Status

I get working streams from both cameras, sending them out at 30fps at 720p.
frigate, however limits the display fps to 5, which is depressing to watch, especially since the tpu doesnt even break a little sweat.

Frigate claime that the TPU is good for up to 10 cameras, so there is headroom.

The stram is completely errant and drops frames left and right. I have sometimes seen detect fps of 0.2, but the TPU speed should definitely not be the bottleneck here. Maybe attach the cameras to a separate device and stream from there?

The biggest issue here is that the google folx seems to have abandoned the coral, even though they just released a new piece of hardware for it.
Their most RECENT python build is 3.9.
Specifically, pycoral seems to be the problem there. without a decent update, I will be confined to debian 10, with python 3.7.3.
That sucks.
There are custom wheels, but nothing that seems plug and play.

About the rest of this setup:
The decision to go for m.2 E key to save money, instead of spending more on the usb version was a huge mistake.
Please do yourself a favor and spend the extra 40 bucks.
Technically, its probably faster and better with continuous operation, but i have yet to feel the benefit of that.

### TODOs

- add images screenshots to the build log
- Check whether vdo.ninja is a viable way to add mobile streams. then Smartphone stream evaluation would be on the horizon.
- Bother the mediamtx makers about the libcamera bump, so we can get rid of the rpicam-vid hack.
I suspect there is quirte a lot of performance lost there.
- tweak the frigate config to get snapshots and maybe build an image / video database to later train a custom model.
- worry about attaching an external ssd and saving the video files on it.
- find a way to export the landmark points from frigate. maybe send them via osc like in pose2art?
- find a different hat that lets me access the other TPU? I have the dual version, but can currently only acces 1 of the 2 TPUs due to hardware restrictions.
