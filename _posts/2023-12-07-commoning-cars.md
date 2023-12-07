---
title:  "Commoning Cars"
author: "Aron Petau"
excerpt: "How can we attack the privatization of public space through cars?"
tags:
  - war on cars
  - public spaces
  - commons
  - urban intervention
  - UdK Berlin
---

## Commoning cars

## TCF Project Brief

Aron Petau
[aron@petau.net](<mailto:aron@petau.net>)

[See the Project in Realtime](https://www.aronpetau.me/ulli/)

## Title

Making Cars Public spaces

## Abstract

Cars bad.
Cars occupy public spaces resulting un a factual privatization of public goods/infrastructure.
What if cars could be part of public infrastructure?
What can cars provide to the public?
With Solar and Electrical Vehicles emerging on the horizon (no endorsement here) it makes sense to think about cars as decentralized powerhouses and public energy storage solutions. Cars, even traditional ones, come equipped with batteries and generate electricity either by driving or though added solar panels. What if this energy could be used to power the public? What if cars would could be used as public spaces?
By installing a public USB socket and a public wifi hotspot, on my car, I want to start exploring the potential of cars as public spaces and energy storage solutions.
Within this artistic experiment, I will continuously track the geolocation and energy input/output of my solar equipped car and make the data publicly available. I will also track the amount of energy that is not used by the car and could be used by the public. Taking steps towards optimal usage of existing electrical and other infrastructure is only possible by breaking conventional notions of public ownership and private property. This project is one step towards a more sustainable and equitable future.

## Introduction

We all know by now that cars and individual traffic presents a major environmetal and societal problem all over the world. The last 70 something years of building car infrastructure are culminating in many areas in a dead end where the only thinkable solution is to build more roads and cars.
THis is obviously a larger problem than one project can tackle, but here is one outlook on how

## Experiment

### Preexisting data

With the data collected over the last year of using the car privately I can show with embarrasing accuracy how underutilized the system is and calculate an estimate of energy lost due to societal notions of private property.
The data will be an estimate, since the monitoring itself is dependent on solar energy and the internet connection is spotty at best when it is not supplied with electricity.

### Monitoring

In the Car, there is a Raspberry Pi 4 Microcomputer running a custom Operating Systen that monitors the following data:

- Solar Intake (W)
- Battery Level (V)
- GPS Location
- Total Energy Produced (Wh)
- Total Energy Consumed (Wh)
- Solar Energy Potential (Wh)

Through the router I can also track total Wifi usage and the number of connected devices.

### Public Wifi

For the Project, I opened a router in the Car towards the Public, much alike to ahotspot you would find in a cafe. I use my own data plan on there, which i never max out anyways. The router is a Netgear M1 and has a 4G Modem built in. It is connected to the Raspberry Pi and is powered by the secondary car battery.

### Public Energy: A USB Socket

I plan on installing a USB Socket on the outside of the car, so people can charge their devices. The socket will be connected to the secondary car battery and will be powered by the solar panels. The socket will be installed in a way that it is not possible to drain the battery completely.

### Communication

Nobody expects any help or public supplies from car owners.
How to communicate the possibility to the outside world?
The plan is to fabricate a vinyl sticker that will be applied to the car. The sticker will contain a QR Code that will lead to a website with the data and a short explanation of the project. Visual cues lead to the USB Socket and the Wifi Hotspot.

## Issues

### Space / Scale

Obviously, the space on top of a car is quite limited and from a sustainability perspective, it would be better to have a larger solar array on a roof of a house. The point is not to advocate for a mandated solar install on cars, but to optimize and share preexisting infrastructure. The car is already there, it already has a battery and it already has solar panels. Looking at many Camper-Van builds, the amount of cars with already installed solar panels is quite large. The point is to make the most out of it.

### Legality

Germany has laws in place holding the owner of a Internet Connection liable for the legality of the traffic that is going through it. This is a major issue for the project, as I do not want to be liable for the traffic that is going through my car. I am currently looking into ways to circumvent this issue.

### Surveillance / Privacy

The Car is equipped with a GPS Tracker and a Wifi Hotspot. This means that I can track the location of the car and the number of devices connected to the hotspot. I am not tracking any data that is going through the hotspot, but I could. As this project will generate public data, People using and maybe depending on the internet and electricity provided will be tracked by proxy. I am not sure how to deal with this issue yet. One potential solution would be to publish the data only in an aggregated form, but this would make the data less useful for other projects.

### Security / Safety

My Car is now publicly traceable. I am no Elon Musk, and the idea does not really concern me, but we did create an additional attack vector for theft here.

## Sources

[UN Sustainable Development Goal Nr. 7](https://sdgs.un.org/goals/goal7)
[Adam Something on the Rise of Urban Cars](https://www.youtube.com/watch?v=lrfsTNNCbP0)
[Is Berlin a walkable City?](https://storymaps.arcgis.com/stories/b7437b11e42d44b5a3bf3b5d9d8211b1)
[FBI advising against utilizing public infrastructure](https://www.fbi.gov/how-we-can-help-you/scams-and-safety/on-the-internet)
[Why no solar panels on cars?](https://www.forbes.com/sites/billroberson/2022/11/30/why-doesnt-every-electric-car-have-solar-panels/?sh=4276c42d1ac6)

---

## Notes

Ideas on Data Mapping workshop

I have the Solar Data from the Van.

It holds Geocodes,
has hourly data
and could tell the difference between geocoded potential solar energy and actual energy.
It also has temperature records.

There are 2 types of Losses in the system:

- Either the Batteries are full and available energy cannot be stored
- Or the solar panels are blocked through urban structures and sub-optimal parking locations.

Interesting Questions:

How far away from optimal usage are my panels and where does the difference stem from?

Where to go?

I think, the difference between potential energy and actual electricity produced/consumed is interesting.
How large is the gap?
 Is it relevant —> my initial guess would be that it is enormous
How to close the gap?

—> install outside usb plugs
 It would be publicly available infrastructure, people could charge their smartphones anywhere
 —> QI charging for security concerns??

Scaling??
—> mandate solar roofs for cars? How effective would it actually be?
 What about buses / public vehicles?

---
Potential issues with the data:

Spotty / intermittent internet connection

Noisy?

Making Cars public spaces

What could my car provide to the public to be less wasteful with its space?

- Provide Internet
  - Would incur monthly costs
- Provide Electricity

Concrete Problems:
 How to make sure people cannot fully drain my battery?
 How dangerous is actually an exposed USB Socket?
  Can people short my electronics through it?
  
 How scalable are solutions like these?

 Are public USBC Sockets something that would actually be used?
 Could there be a way for people to leave their stuff charging?
  What if I actually move the car?

 Can cars provide positive effects to public spaces?
  —> how to pose this research question without redeeming the presence of cars in our public spaces?

 Difference Electric - Fuel cars

 Lots of research on using Electric cars as state storage

 <div id="adobe-dc-view" style="width: 800px;"></div>
<script src="https://acrobatservices.adobe.com/view-sdk/viewer.js"></script>
<script type="text/javascript">
 document.addEventListener("adobe_dc_view_sdk.ready", function(){
  var adobeDCView = new AdobeDC.View({clientId: "7e638fda11f64ff695894a7bc7e61ba4", divId: "adobe-dc-view"});
  adobeDCView.previewFile({
   content:{location: {url: "https://acrobatservices.adobe.com/view-sdk-demo/PDFs/Bodea Brochure.pdf"}},
   metaData:{fileName: "Bodea Brochure.pdf"}
  }, {embedMode: "IN_LINE", showPrintPDF: false});
 });
</script>
