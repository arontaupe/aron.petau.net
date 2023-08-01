---
title:  "Lampshades"
excerpt: "An exploration of the depths of rhino/grasshopper"
date:   2022-12-04 14:39:27 +0100
last_modified_at: 2021-05-11T10:23:16-04:00
author: "Aron Petau"
tags:
- rhino
- grasshopper
- parametric
- lamp
- lampshade
- private
- 3D
- printing
- 3D printing
- Studio D+C
- TODO, unfinished

header:
  overlay_image: /assets/images/lampshades/lampshade4.heic
  overlay_filter: 0.5
  credit: "Aron Petau"


gallery:
  - url: /assets/images/lampshades/lampshade1.heic
    image_path: /assets/images/lampshades/lampshade1.heic
    title: "A parametric lampshade made with rhino and grasshopper"
  - url: /assets/images/lampshades/lampshade2.jpeg
    image_path: /assets/images/lampshades/lampshade2.jpeg
    title: "A parametric lampshade made with rhino and grasshopper"
  - url: /assets/images/lampshades/lampshade3.heic
    image_path: /assets/images/lampshades/lampshade3.heic
    title: "A parametric lampshade made with rhino and grasshopper"
  - url: /assets/images/lampshades/lampshade4.heic
    image_path: /assets/images/lampshades/lampshade4.heic
    title: "A parametric lampshade made with rhino and grasshopper"
  - url: /assets/images/lampshades/lampshade5.jpeg
    image_path: /assets/images/lampshades/lampshade5.jpeg
    title: "A parametric lampshade made with rhino and grasshopper"

gallery2:
  - url: /assets/images/lampshades/gh_lampshade_flow.png
    image_path: /assets/images/lampshades/gh_lampshade_flow.png
    title: "the grasshopper flow for the lampshade"
  - url: /assets/images/lampshades/grasshopper_lampshade_flow.png
    image_path: /assets/images/lampshades/grasshopper_lampshade_flow.png
    title: "the grasshopper flow for the lampshade"
  - url: /assets/images/lampshades/result_rhino.png
    image_path: /assets/images/lampshades/result_rhino.png
    title: "The resulting lampshade in rhino"

created: 2023-07-27T00:01:27+02:00
updated: 2023-07-27T00:16:33+02:00
---

## Lampshades

During 2022, I was exposed to some of the awesomenest tools for architects.
One of them was Rhino, a 3D modeling software that is used for a lot of architectural design. 
I hate it. It has quite an unreadable interface and is not very intuitive, with straight-up 80s vibes.
It has plugins though, and one of them is Grasshopper, a visual programming language that is used to create parametric models.
Grasshopper is insanely powerful and seems to be a full-fledged programming language, but it is also very intuitive and easy to use, rather similar to the new node-based flows unreal engine and blender are now starting.
Sadly, grasshopper does not come as a standalone, and it requires Rhino to run and achieve many of the modeling steps.

In that combination, Rhino suddenly becomes much more appealing, and I started to enjoy the process of modeling in it.
I was able to create a parametric lampshade that I am very happy with and can modify on the fly for ever-new lampshades.

Then printing it with white filament in vase mode was a breeze and here you can see some of the results.

{% include gallery %}

{% include gallery id="gallery2"  caption="The Results" %}