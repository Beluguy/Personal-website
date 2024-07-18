---
title: "Qi compatible wireless charger"
date: 2024-07-14
lastmod: 2024-07-18
# Description: 
tags: ["hobby", "Qi", "wireless charger", "PCB", "magnetic induction", "Altium Designer"]

showDate : true
showDateOnlyInArticle : false
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

Since Youssef and I wanted to deepen our understanding of electrical engineering, we prefer to go with RF or mangnetic induction. Comparing the two options, we found that most mobile devices like smartphones and smartwatches made in recent years can charge via magetic induction, there should be plenty of resources for us to learn from. So, we decided to look at magnetic induction. 

## What is magnetic induction?
Magnetic induction wirelessly transfer energy between the charger/transmitter (TX) coil and load/receiver (RX) coil via a time varying magnetic field. When the magnetic field is captured by the RX coil, it induces a voltage across the termainals of RX coil in accordance with Faraday's law, as shown below. 

Faraday's law: {{<katex>}}\\({\displaystyle{\mathcal{E}}}=-N\frac{dΦ}{dt}\\) where {{<katex>}}\\(N\\) = # of turns of the coil; {{<katex>}}\\(Φ\\) = magnetic flux; {{<katex>}}\\(t\\) = time

![](images/how-it-works.png "Credit: [Thomson Reuters](https://blogs.thomsonreuters.com/answerson/wp-content/uploads/sites/3/2016/06/pdfnews-e1410790372461.jpg)")

However, this system is not inherently safe due to an effect called parasitic heating. Parasitic heating happens when any metal object comes near the TX coil while it is transmitting. The object can rapidly heats up due to the induced eddy current inside the object from the time varying magnetic field. 

To mitigate this, we need some kind of foreign obejct detection (FOD) system. That brings us to the Qi protocol. 


## What is the Qi protocol?
Qi (pronounced “chee”) is created by the [Wireless Power Consortium (WPC)](https://www.wirelesspowerconsortium.com), which is a group of companies that promote and develop standards for wireless power transmission. It is comprised of over 300 member companies from across the world such as Apple, Sony, Samsung, and Microsoft. 

Qi is argueably the most widely adopted standards within the consumer electronics market, especially for charging smartphones and wearables. The Qi standard ensures interoperability and security between Qi-enabled devices, allowing them to charge using any wireless chargers that are Qi compatible or certified (for Qi v2).

The Qi protool has a foreign object detection (FOD) that 




