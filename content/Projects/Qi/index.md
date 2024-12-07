---
title: "Qi compatible wireless charger (WIP)"
date: 2024-07-14
lastmod: 2024-07-26
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

Since Youssef and I wanted to deepen our understanding of electrical engineering, we prefer to go with RF or mangnetic induction. Comparing the two options, we found that most mobile devices like smartphones and smartwatches made in recent years can charge via magetic induction. So, there should be plenty of resources for us to learn from. Therefore, we decided to look at magnetic induction. 


## What is magnetic induction?
Magnetic induction is a process that wirelessly transfer energy between the charger/transmitter (TX) coil and load/receiver (RX) coil via a time varying magnetic field. When the magnetic field is captured by the RX coil, a voltage is induced across the termainals of RX coil in accordance with Faraday's law, as shown below. 

Faraday's law: {{<katex>}}\\({\displaystyle{\mathcal{E}}}=-N\frac{dΦ}{dt}\\) where {{<katex>}}\\(N\\) = # of turns of the coil; {{<katex>}}\\(Φ\\) = magnetic flux; {{<katex>}}\\(t\\) = time

![](images/how-it-works.png "Credit: [Thomson Reuters](https://blogs.thomsonreuters.com/answerson/wp-content/uploads/sites/3/2016/06/pdfnews-e1410790372461.jpg)")

However, this system is not inherently safe due to an effect called parasitic heating. Parasitic heating happens when any electrically conductive material comes near the TX coil while it is transmitting. The material can rapidly heats up due to the induced eddy current inside from the time varying magnetic field. 

To mitigate this, we need some kind of foreign obejct detection (FOD) system. That brings us to the Qi protocol, which has FOD as part of the specification. 


## What is the Qi protocol?
Qi (pronounced “chee”) is created by the [Wireless Power Consortium (WPC)](https://www.wirelesspowerconsortium.com), which is a group of companies that promote and develop standards for wireless power transmission. It is comprised of over 300 companies around the world such as Apple, Sony, Samsung, and Microsoft. 

Qi is argueably the most widely adopted standards within the consumer electronics market, especially for charging smartphones and wearables. The Qi standard has ensures interoperability and security between Qi-enabled devices, allowing them to charge using any wireless chargers that are Qi compatible and/or certified (for Qi v2).

Qi has many features, below are some of the more important ones (in my opinon).

#### Power levels & Compatibility
A Qi TX is capcable of transfering at least 5 W of power and up to the architectural limit of about 30 W. However, the actual amount of power transferred is subject to negotiation between the RX and TX. This communication assures interoperability between Qi wireless products
in the Baseline Power Profile (BPP), which is less than or equal to 5 W, and in the Extended Power Profile (EPP), which is up to 15 W.

For example, if a RX is designed to be charged by a 15 W TX but is placed on a 5 W TX, theRX may allow charging at a slower rate. Conversely, if a 5 W RX is placed on a 15 W TX, the RX will tell the TX to send no more than 5 W of power.

#### Foreign object handling & Safety
As mentioned in the [What is magnetic induction](#what-is-magnetic-induction) section, any electrically conductive material that are exposed to a time varying magnetic field can rapidly heats up due to the induced eddy currents inside the object. To reliably detect such foreign objects, the TX needs to receive appropriate information from each RX it is serving. The Qi specification defines the kind of information that a RX has to provide for this purpose, such as the RX's reference resonance frequency and reference quality factor. 

However, the specification does not define a single method for foreign object detection (FOD) that a TX has to apply. Instead, compliance testing verifies that a TX does not heat up a set of reference foreign objects in a set of reference scenarios. 

Since we don't plan to do any expensive compliance testing, we will make sure our charger does not overheat by using sensors to monitor its temperature and stop transmitting when it reaches a threshold. In addition to that, we will have a FOD that also stop the tranmission when a foreign object is detected.


## How does the Qi (v1.3) protocol works?
Although the latest Qi protocol is at v2.0 (as of the July, 2024), we are going to explain the high level overview of the charging procoess of version 1.3 because that is the latest specification available to non WPC members. Below is a high level overview of the charging procoess. Noted that the Negotiation phase is not present in the Baseline Protocol. 

#### 1. Ping Phase
When TX is idling, it is in the Ping Phase, the TX tries to establish communications with a RX. Before doing so, it typically performs measurements to determine if there are objects such as bankcards, coins or other metals, which can damage or heat up during the power transfer. These measurements proceed without waking up the Power Receiver.

#### 2. Configuration Phase


#### 3. Negotiation Phase 


#### 4. Power Transfer Phase