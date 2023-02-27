---
title: "Reflow Oven Controller"
date: 2023-02-26
hero: images/controller.jpg
# description: Breif explanations of the DJI FPV drone repair process
menu:
  sidebar:
    name: Reflow Oven Controller
    identifier: Reflow-Oven-Controller
    parent: Projects
    weight: 9
tags: ["hobby", "fpv", "drone", "repair"]
author: 
  name: Marcus
---
My teammates and I designed and built a reflow oven controller that controls the temperature of an oven via a PWM signal to an SSR box. The reflow parameters such as reflow temperature, reflow time and cool down temperature can be adjust. The parts we used can be found via this [link to github](https://github.com/Beluguy/Elec-291/blob/main/reflow-oven-controller/Spec.md).
![controller](images/controller.jpg)
To verify that our controller is working, we made a board using our controller. It is perfect!👌We then hand solder the header pins and the USB port to it after.
![efm8](images/efm8.jpg)