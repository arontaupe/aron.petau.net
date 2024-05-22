---
title:  "Echoing Dimensions"
excerpt: "An interactive audiovisual installation."
date:   2024-04-25 14:39:27 +0100
authors: 
  - Aron Petau
  - Joel Tenenberg

header:
  overlay_image       : assets/images/echoing_dimensions/Echoing Dimensions-4.jpg
  teaser              : assets/images/echoing_dimensions/Echoing Dimensions-4.jpg
  overlay_filter      : 0.5
  credit              : Aron Petau
tags:
  - university of the arts berlin
  - university
  - studierendenwerk
  - exhibition
  - installation
  - touchdesigner
  - micropython
  - raspberry pi pico
  - ultrasonic sensor
  - tts
  - radio
  - fm
  - radio-art
  - kinect
  - pointcloud
  - llm
  


gallery:
 - url: assets/images/echoing_dimensions/Echoing Dimensions-4.jpg
   image_path: assets/images/echoing_dimensions/Echoing Dimensions-4.jpg
   title: "The FM Transmitter"
 - url: assets/images/echoing_dimensions/Echoing Dimensions-1.jpg
   image_path: assets/images/echoing_dimensions/Echoing Dimensions-1.jpg
   title: "Video Output with Touchdesigner"
 - url: assets/images/echoing_dimensions/Echoing Dimensions-2.jpg
   image_path: assets/images/echoing_dimensions/Echoing Dimensions-2.jpg
   title: "One of the Radio Stations"
 - url: assets/images/echoing_dimensions/Echoing Dimensions-7.jpg
   image_path: assets/images/echoing_dimensions/Echoing Dimensions-7.jpg
   title: "The Diagram"
 - url: assets/images/echoing_dimensions/Echoing Dimensions-13.jpg
   image_path: assets/images/echoing_dimensions/Echoing Dimensions-13.jpg
   title: "The Network Spy"
 - url: assets/images/echoing_dimensions/IMG_1709.jpeg
   image_path: assets/images/echoing_dimensions/IMG_1709.jpeg
   title: "The Exhibition Setup"
---

## Echoing Dimensions

## The space

[Kunstraum Potsdamer Straße](https://www.stw.berlin/kultur/kunstraum/kunsträume/)

The exhibition is situated in an old parking garage, owned and operated by the studierendenwerk Berlin. The space is a large, open room with a rather low ceiling and a concrete floor. Several Nooks and separees can create intimate experiences within the space. The space is not heated and has no windows. The walls are made of concrete and the ceiling is made of concrete.

As a group, we are 12 people, each with amazing projects surrounding audiovisual installations:

- Özcan Ertek (UdK)
- Jung Hsu (UdK)
- Nerya Shohat Silberberg (UdK)
- Ivana Papic (UdK)
- Aliaksandra Yakubouskaya (UdK)
- Aron Petau (UdK, TU Berlin)
- Joel Rimon Tenenberg (UdK, TU Berlin)
- Bill Hartenstein (UdK)
- Fang Tsai (UdK)
- Marcel Heise (UdK)
- Lukas Esser & Juan Pablo Gaviria Bedoya (UdK)

## The Idea

We will be exibiting our Radio Project,
[aethercomms](/aethercomms/)
which resulted from our previous inquiries into cables and radio spaces during the Studio Course.

## Build Log

### 2024-01-25

First Time seeing the Space:

{% include video id="UaVTcUXDMKA" provider="youtube" %}

### 2024-02-01

Signing Contract

### 2024-02-08

The Collective Exibition Text:

>Sound, as a fundamental element of everyday experience, envelopes us in the cacophony of city life - car horns, the chatter of pedestrians, the chirping of birds, the rustle of leaves in the wind, notifications, alarms and the constant hum of radio waves, signals and frequencies. These sounds, together make up the noise of our life, often pass by, fleeting and unnoticed.
The engagement with sound through active listening holds the potential to process the experience of the self and its surroundings. This is the idea of “Echoing Dimensions”: Once you engage with something, it gives back to you: Whether it is the rhythmic cadence of a heartbeat, a  flowing symphony of urban activity or the hoofbeats of a running horse, minds and bodies construct and rebuild scenes and narratives while sensing and processing the sounds that surround them, that pass next and through them.
The exhibition "Echoing Dimensions" takes place at Kunstraum Potsdamer Straße gallery’s underground space and exhibits artworks by 12 Berlin based artists, who investigate in their artistic practice ‘intentional listening’ using sound, video and installation, and invites to navigate attentiveness by participatory exploration. Each artwork in the exhibition revolves around different themes in which historical ideas resonate, political-personal narratives are being re-conceptualized and cultural perspectives are examined. The exhibition's common thread lies in its interest into the complexities of auditory perception, inviting viewers to consider the ways in which sound shapes our memories, influences our culture, and challenges our understanding of space and power dynamics.

### 2024-02-15
Working TD Prototype. We collect the pointcloud information through a kinect azure and sorting the output of the device turned out to be quite tricky. 

### 2024-03-01
Initial live testing on the finalized hardware. We decided to use a tiny Intel NUC to run both touchdesigner, the LLM, and audio synthesis.

Not expected at all: The audio synthesis was actually the hardest, since there was no available internet in the exhibition space and all sleek modern solutions seem to rely on cloud services to generate audio from text. 
Here, the tiny NUC really bit us: it took almost 15 seconds to generate a single paragraph of spoken words, even when usin quite small synthesizer models for it. 

Lesson learned: Next time give it more oomph. 
I seriously wonder though why there wouldn't be better TTS systems around. Isnt that quite the essential accessibility feature?  We ended up using coquiTTS, which is appearently out of business entirely. 


### 2024-04-05
We became part of [sellerie weekend](https://www.sellerie-weekend.de)!

![Sellerie Weekend Poster](/assets/images/echoing_dimensions/sellerie_weekend.png)

This is a collection of Gallery Spaces and Collectives that provide a fresher and more counter-cultural perspective on the Gallery Weekend.
It quite helped our online visibility and filled out the entire space on the Opening.


### A look inside
{% include video id="qVhhv5Vbh8I" provider="youtube" %}

{% include video id="oMYx8Sjk6Zs" provider="youtube" %}


### The Final Audiovisual Setup

{% include gallery %}