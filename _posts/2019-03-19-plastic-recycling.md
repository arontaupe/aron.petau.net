---
title:  "Plastic Recycling"
date           :   2022-03-01 14:39:27 +0100
author: "Aron Petau"
header:
  image: "/assets/images/recycling_graphic.png"
  credit              : "Aron Petau"
last_modified_at: 2021-05-11T10:23:16-04:00
tags:
  - decentral
  - democratic
  - precious plastic
  - plastics
  - recycling
  - circular
  - cradle-to-cradle
  - automatic
  - ml
  - Arduino
  - Linux
  - waste
  - filastruder
  - private
  - master thesis
  - waste
  - sustainability
  - environment
  - 3D printing
  - filament
  - shredder
created: 2023-07-26T23:59:37+02:00
updated: 2023-07-27T00:14:37+02:00
---

Being involved with 3D Printers, there is the issue of sustainability that I am confronted with regularly. 
Most 3D printed parts never get recycled and add to the global waste problem, rather than reducing it.
The printer most certainly doesn’t care what it is printing, the main problem is the dimensional accuracy and the purity of the material. All of this leads to a huge industry, Germany being especially involved, using loads of virgin plastic. 

What can be done about it?
We can design our products to last longer, we can also print recycling labels on them so they do not have to get burned after their first life. We can take care to only print functional objects, not just fun toys nobody uses.
Yet, none of that prevents the use of virgin plastics. If you buy a spool of filament, there are some recycled options, but usually at twice the price at worse quality. No wonder recycled filament fails to convince the masses. It is mostly a fun thing YouTubers can pursue, not a valid commercial process.

{% include video id="vqWwUx8l_Io" provider="youtube" %}

In my opinion, the core problem is the nonexistent economic feasibility of a proper recycling process. Identifying the exact material of a piece of trash is a very hard problem, definitely not solved yet. So why do we mix the plastic up in the first place? There is a general willingness of people to recycle, but the system for it is missing.

# The Master Plan
I want to get people to wash and separate their trash for me, which are the most expensive steps in the recycling process. There is willingness to take the extra step, and even if just my mom collects bottle caps for me, that is more than I can realistically use up.
This only really works when I am thinking in a local and decentral environment.
The existing recycling facilities clearly will not be able to provide 200 different containers for 200 different types of plastic.
Starting the process with clean and sorted materials, like bottle caps (HDPE) or failed prints (PET-G), I start off with an advantage.
Now I have to take apart the trash into evenly sized particles.
Meet:

## The Shredder

We built the Precious Plastic Shredder!

<iframe width="510" height="682" src="https://b2b.partcommunity.com/community/partcloud/embedded.html?route=embedded&name=Shredder+Basic+V2.0&model_id=96649&portal=b2b&showDescription=true&showLicense=false&showDownloadButton=false&showHotspots=true&noAutoload=false&autoRotate=true&hideMenu=false&topColor=%23dde7ed&bottomColor=%23ffffff&cameraParams=false&varsettransfer=" frameborder="0" id="EmbeddedView-Iframe-96649" allowfullscreen></iframe>

With these awesome open-source drawings, I was able to cobble together my very own very dangerous plastic shredder.

After finding some way to drive this massive axis, I feed the beast and hopefully get tiny pretty uniform plastic bits that are ready to begin the cycle of life anew.

The solution for the motorization was an old and used garden shredder that still had an intact motor and wiring.
We cut it in half and attached it to the shredder box.

{% include video id="QwVp1zmAA4Q" provider="youtube" %}

After replacing the weak force transmission screw for an industrial coupler, we were ready to try it out. Obviously, there are still security concerns in this prototype, a proper hopper is already being made.

Nevertheless, we are confident that this shredder will be able to deal with the light sorts of plastic we are thinking of.
As you can see, I am now able to produce awesome confetti but to do more with the plastic flakes I have to extrude them.

## Meet the Filastruder

This is the Filastruder, designed and made by Tim Elmore, in an attempt to create the cheapest viable way to extrude plastic. The biggest cost issue is the tight industrial tolerances in thickness that have to be adhered to. This is in essence what separates good from the bad filament. The industry standard nowadays is at +-0.03mm. Hard to achieve on a DIY setup, but not unheard of. The setup, like any bigger industry equivalent, consists of a motor pressing plastic pellets through a heated screw, extruding molten plastic at the end through a nozzle, and setting the diameter. The leftmost machine is responsible for winding the filament properly onto a spool.

Here you can see the extrusion process in action.

{% include video id="FX6--pYrPVs" provider="youtube" %}

The Filastruder is controlled by an Arduino and is highly configurable. The laser sensor visible in the video is already working, but I am missing more direct control over the diameter of the filament.

When it all really comes down to the single variable of the filament diameter responsible for the quality of my recycled project, a simple Machine Learning optimization directly jumps at me: I have a few variables like winder speed, extrusion speed, heat, and cooling intensity. These variables can be optimized on the fly for an exact diameter. This is actually roughly how virgin filament is produced, commercial facilities just manage much faster.

![The variables in an iterative optimization](/assets/images/recycling_variables.png)
So far, I am aware of a few companies and academic projects attempting this process, but none of them manage to get either the quality or the price of other products available. Automatization does not just take out jobs away, I think it can also be a helpful tool, for example tackling environmental issues such as this one.


This project is very dear to my heart and I plan to investigate it further in the form of a master thesis.
The realization will require many skills I am already picking up or still need to work on within the Design and Computation program. 
{: .notice--info}


[Reflow Filament](https://reflowfilament.com/){: .btn .btn--large}

[Perpetual Plastic Project](https://www.perpetualplasticproject.com/){: .btn .btn--large}

[Precious Plastic Community](https://preciousplastic.com/){: .btn .btn--large}

[Filamentive Statement on why recycling is not feasible in their opinion ](https://www.filamentive.com/recycling-failed-and-waste-3d-prints-into-filament-challenges/
){: .btn .btn--large}

[Open source filament diameter sensor by Tomas Sanladerer ](https://www.youmagine.com/designs/infidel-inline-filament-diameter-estimator-lowcost-10-24){: .btn .btn--large}

[Re-Pet Shop ](https://re-pet3d.com/s){: .btn .btn--large}

