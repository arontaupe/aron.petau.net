---
title:  Ruminations
excerpt: Perspectives on Engineering
date:   2023-03-01 14:39:27 +0100
last_modified_at:   2023-03-01 14:39:27 +0100
authors: 
  - Aron Petau
  - Niels Gercama
  
header:
  teaser: /assets/images/ruminations/ruminations1.jpeg
  overlay_image: /assets/images/ruminations/ruminations1.jpeg
  overlay_filter: 0.5
  credit: Aron Petau

gallery:
- url: /assets/images/ruminations/ruminations1.jpeg
  image_path: /assets/images/ruminations/ruminations1.jpeg
  alt: ""
  title: "The projects installation"
- url: /assets/images/ruminations/ruminations2.jpeg
  image_path: /assets/images/ruminations/ruminations2.jpeg
  alt: ""
  title: "The projects installation"
- url: /assets/images/ruminations/ruminations3.jpeg
  image_path: /assets/images/ruminations/ruminations3.jpeg
  alt: ""
  title: "The projects installation"
 
tags:
    - journal
    - javascript
    - computer vision
    - data privacy
    - capitalism
    - pattern recognition
    - image classifier
    - consumerism
    - browser fingerprinting
    - amazon
    - data privacy
    - data
    - privacy
    - studio d+c
    - university of the arts berlin
    - udk
    - TODO, unfinished
---
## Ruminations

was a contemplation on data privacy at Amazon.
It asks how to subvert browser fingerprinting and evading the omnipresent tracking of the consumer.

The initial idea was to somehow, by interacting with the perpetrator and letting data accumulate that would degrade their knowledge and thereby destroy predictablity, making this particular dataset worth less.

We could have just added a random clickbot, to confuse things a bit and make the data less valuable.
But looking at todays state of datacleanup algorithms and the sheer amount of data that is collected, this would have been a futile attempt. Amazon just detects and removes any noise we add and continues to use the data.

So, then, how can we create coherent, non-random data that is still not predictable?

One answer that this concept should demonstrate, is by inserting patterns that amazon cannot foresee with their current algorithms. As if they were trying to predict the actions of a person with shizophrenia.

## The Concept

It consists of a browser extension (currently Chrome only) that overlays all web pages of Amazon with a moving entity that tracks your behavior. While tracking, an image classifier algorithm is used to formulate a product query off of the Storefront. After computation, a perfectly fitting product is displayed for your consumer's pleasure.

## The analogue watchdog

A second part of the project is a low-tech installation consisting of a camera (we used a smartphone) running a computer-vision algorithm tracking tiny movements. This was then pointed towards the browser console in the laptop running the extension. The camera was then connected to a screen that displayed the captured image. The watchdog was trained to make robot noises depending on the type and amount of movement detected. Effectively, whenever data traffic beween amazon and the browser was detected, the watchdog would start making noises.

# The Browser extension

TODO: add photo

{% include gallery %}

### Find the code on GitHub

Subvert a bit yourself, or just have a look at the code.
[The code of the Project on GitHub](https://github.com/arontaupe/ruminations){: .btn .btn--large}

TODO: create video with live demo
