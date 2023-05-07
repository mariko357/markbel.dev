---
title: "Blinky"
date: 2023-05-02T23:27:14+03:00
draft: false
author: "Marko"
type: "post"
description: "A small and fun project."
tags:
    - "pcb"
aliases:
katex: false
markup: "mmark"
twitterCreator: ""
twitterSite: ""
twitterImg: "/android-chrome-192x192.png"
ogImage: "/android-chrome-192x192.png"
ogType: "article"
---


It seems that everyone's road to electronics starts from some sort of blinky - a small project based on something like a 555 circuit or microcontroller. 
Mine wasn't different.

![](/img/blinky/prod-top.jpg)

Originally, this project was intended to be a Valentine's gift, but ended up being over a month late)
The design itself was done in 3 to 4 days, but manufacturing and shipping took ten times more.

***
## Overall features:
The project is based on a `stm32` ucontroller and 3 8-bit shift registers, which is just enough to make a 12x12 matrix that is lit up with dynamic 
indication. The outline dimensions are of standard-size credit card. _Why?_ To be honest, I don't really know, I think took inspiration from someone making 
a [game of snake in the same size](https://bigfootcreations.wordpress.com/2022/12/31/pcb-business-card/). The design was made in KiCad and software part of things
was done in STM32CubeIDE. At first, I calculated every frame by hand, but then made a small [app](https://l.markbel.dev/converter) to convert to do it for me.

![](/img/blinky/kicad-pcb-top.png)

***

## More technical details:
The board uses `stm32g030f6p6` as its main controller, there wasn't any specific reason why I chose this chip, I just had it lying around.
Each column is routed through a mosfet, and rows are directly connected to shift registers. The board has a button with a capacitor to get rid of bouncing
and a voltage divider connected to the MCU to sense the battery voltage.

The microcontroller wakes up on button click, displays image for a set time, and then again goes to sleep.

I`ve actually had problems with the sleep mode, where one of the microcontrollers didn't go into it, and stayed in run mode, 
draining around 10mA continuously. This clearly wasn't an option, because the battery would only last around 20 hours. 
I tried to debug it for several days with no luck, only to discover that the other board was working flawlessly. I still haven't 
found out why it wasn't functioning on the first one.

![](/img/blinky/dev-board-assembled.jpg)
First board with wires soldered to it and some traces cut.

***


- [CAD files and code](https://github.com/mariko357/blinky)
- [Converter app](https://converter.markbel.dev)
- [Converter app repo](https://github.com/mariko357/bitmap-converter)