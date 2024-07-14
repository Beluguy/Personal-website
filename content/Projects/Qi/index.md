---
title: "Qi compatible wireless charger"
date: 2024-07-14

# Description: 
tags: ["hobby", "Qi", "wireless charger", "PCB", "magnetic induction", "Altium Designer"]

showDate : true
showDateOnlyInArticle : false
draft: true
showDateUpdated : true
showHeadingAnchors : false
showPagination : false
showReadingTime : true
showTableOfContents : true
showTaxonomies : true 
showWordCount : true
showSummary : false
sharingLinks : false
showEdit: false
showViews: false
showLikes: false
layoutBackgroundHeaderSpace: false
---

## TL;DR
[Youssef](https://linkedin.com/in/youssef-chaabani) and I are making a Qi compatible wireless charger. 

## What is wireless charging?
Wireless charging simply refers to the transfer of energy without the need of a physical connection between the charger and the load. There are various ways a charger can transmit energy wirelessly. For example, via [ultrasound](https://phys.org/news/2024-05-ultrasound-wireless-implantable-biomedical-devices.html), via [radio frequency (RF)](https://airfuel.org/airfuel-rf/), and via [magnetic induction](https://www.wirelesspowerconsortium.com/standards/qi-wireless-charging/).

Since most smartphones and smartwatches made in recent years can charge via magetic induction, there should be plenty of resources for us to learn from. So, we decided to look at magnetic induction. 

## What is magnetic induction?
Magnetic induction wirelessly transfer energy between the charger/transmitter (TX) coil and load/receiver (RX) coil via a time varying magnetic field. When the magnetic field is captured by the RX coil, it induces a voltage across the termainals of RX coil, as shown in the figures below. 
![](images/how-it-works.png "Credit: [Thomson Reuters](https://blogs.thomsonreuters.com/answerson/wp-content/uploads/sites/3/2016/06/pdfnews-e1410790372461.jpg)")

However, this system is not inherently safe due to an effect called parasitic heating. Parasitic heating happens when any metal object comes near the TX coil while it is transmitting. The object can rapidly heats up due to the induced eddy current inside the object from the time varying magnetic field. 

To mitigate this, we need some kind of foreign obejct detection (FOD). That brings us to the Qi protocol. 


## What is the Qi protocol?
Qi (pronounced “chee”) is created by the [Wireless Power Consortium (WPC)](https://www.wirelesspowerconsortium.com). It is the most popular of the wireless charging standards among mobile devices. 

The Qi protool has a foreign object detection (FOD) that 




