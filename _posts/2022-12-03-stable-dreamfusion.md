---
title:  "Stable Dreamfusion"
excerpt: "An exploration of 3D mesh generation through AI"
date:   2023-06-20 14:39:27 +0100
last_modified_at: 2023-06-20 14:39:27 +0100
author: "Aron Petau"
tags:
  - dreamfusion
  - ai
  - 3d
  - mesh
  - generative
  - Studio D+C
  - TODO, unfinished

created: 2023-07-27T00:02:18+02:00
updated: 2023-07-27T00:02:18+02:00
---

## Stable Dreamfusion

<div class="sketchfab-embed-wrapper"> <iframe title="Stable-Dreamfusion Pig" frameborder="0" allowfullscreen mozallowfullscreen="true" webkitallowfullscreen="true" allow="autoplay; fullscreen; xr-spatial-tracking" xr-spatial-tracking execution-while-out-of-viewport execution-while-not-rendered web-share width="800" height="600" src="https://sketchfab.com/models/0af6d95988e44c73a693c45e1db44cad/embed?ui_theme=dark&dnt=1"> </iframe> </div>

## Sources

I forked a really popular implementation that reverse engineered the Google Dreamfusion algorithm. This algorithm is closed-source and not publicly available.
The implementation I forked is [here](https://github.com/arontaupe/stable-dreamfusion)
This one is running on stable-diffusion as a bas process, which means we are are expected to have worse results than google.
The original implementation is [here](https://dreamfusion3d.github.io)

{% include video id="shW_Jh728yg" provider="youtube" %}

## Gradio

The reason i forked the code is so that i could implement my own gradio interface for the algorithm. Gradio is a great tool for quickly building interfaces for machine learning models. No code involves, any user can state their wish, and the mechanism will spit out a ready-to-be-rigged model (obj file)

## Mixamo

I used Mixamo to rig the model. It is a great tool for rigging and animating models. But before everything, it is simple. as long as you have a model with a decent humanoid shape in something of a t-pose, you can rig it in seconds. Thats exactly what i did here.

## Unity

I used Unity to render the model to the magic leap 1. THrough this, i could create an interactive and immersive environment with the generated models.

The dream was, to build a AI- Chamber of wishes. You pick up the glasses, state your desires and then the algorithm will present to you an almost-real object in AR.

Due to not having access to the proprietary sources from google and the beefy, but still not quite machine-learning ready computers we have at the studio, the results are not quite as good as i hoped. But still, the results are quite interesting and i am happy with the outcome. A single generated object in the Box takes roughly 20 minutes to generate. Even then, the algorithm is quite particular and oftentimes will not generate anything coherent at all.
