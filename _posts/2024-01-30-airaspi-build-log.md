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

Rough idea: Build an edge device with image recognitionm and object detection capabilites. it should be realtime
Inspo from: pose2art


work in progress


## Hardware

Raspberry Pi 5
Raspberry Pi Camera Module v1.3
Raspberry Pi GlobalShutter Camera
2x CSI FPC Cable (needs one compact side to fit pi 5)
Pineberry AI Hat (m.2 E key)
Coral Edge TPU (m.2 E key)
Raspi Official 5A Power Supply
Raspi active cooler

## Setup

### Raspberry Pi OS

use raspberry pi imager to flash the latest raspberry pi os lite to a sd card
needs to be bookworm

-- used the default arm64 image (with desktop)
-- enable custom settings:
-- enable ssh
-- set wifi country
-- set wifi ssid and password
-- set locale
-- set hostname: airaspi

### update

```zsh
sudo apt update && sudo apt upgrade -y && sudo reboot
```

### prep system for coral

check kernel version

```zsh
uname -a
```

modify config.txt

```zsh
sudo nano /boot/firmware/config.txt
```

-- add:
kernel=kernel8.img
dtparam=pciex1
dtparam=pciex1_gen=2

-- save and reboot

```zsh
sudo reboot
```

check

```zsh
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

confirm with

```zsh
ls /dev/apex_0
```

### Docker

install docker

```zsh
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```

add user to docker group

```zsh
sudo groupadd docker
sudo usermod -aG docker $USER
```

```zsh
sudo reboot
```

# verify with

```zsh
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

paste:

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

build the docker container

```zsh
docker build -t "coral" .
```

run the docker container

```zsh
docker run -it --device /dev/apex_0:/dev/apex_0 coral /bin/bash
```

run an inference example from within the container

```zsh
python3 /usr/share/edgetpu/examples/classify_image.py --model /usr/share/edgetpu/examples/models/mobilenet_v2_1.0_224_inat_bird_quant_edgetpu.tflite --label /usr/share/edgetpu/examples/models/inat_bird_labels.txt --image /usr/share/edgetpu/examples/images/bird.bmp
```

### Portainer

install portainer

```zsh
docker volume create portainer_data
docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:latest
```

open portainer in browser and set admin password
-- should be available under <https://airaspi.local:9443>

maybe this script is the issue?
i will try again without it

```zsh
curl https://gist.githubusercontent.com/dataslayermedia/714ec5a9601249d9ee754919dea49c7e/raw/32d21f73bd1ebb33854c2b059e94abe7767c3d7e/coral-ai-pcie-edge-tpu-raspberrypi-5-setup | sh
```

-- yes it was the issue, wrote a comment about it on the gist
[comment](https://gist.github.com/dataslayermedia/714ec5a9601249d9ee754919dea49c7e?permalink_comment_id=4860232#gistcomment-4860232)

### raspi-config

```zsh
sudo raspi-config
```

-- enable vnc

### connect through vnc viewer

install vnc viewer on mac
use airaspi.local:5900 as address

### working docker-compose for frigate

start this as a custom template in portainer

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

install mediamtx

```zsh
mkdir mediamtx
cd mediamtx
wget https://github.com/bluenviron/mediamtx/releases/download/v1.5.0/mediamtx_v1.5.0_linux_arm64v8.tar.gz

tar xzvf mediamtx_v1.5.0_linux_arm64v8.tar.gz && rm mediamtx_v1.5.0_linux_arm64v8.tar.gz
```

edit the mediamtx.yml file

```zsh

### frigate

install frigate

```zsh
docker volume create frigate_config
docker volume create frigate_media
docker run -d --name frigate --restart unless-stopped --privileged --shm-size 512M -v /dev/bus/usb:/dev/bus/usb -v frigate_config:/config -v frigate_media:/media -p 5000:5000 blakeblackshear/frigate:stable-rpi
```

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
