---
title: "Impulse"
date: 2023-07-10T10:56:31+03:00
draft: false
author: "Marko"
type: "post"
description: "Impulse - development platform for almost anything that moves."
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

## Impulse - development platform for almost anything that moves.

***

![3d view in KiCAD](/img/impulse/impulse-3dview.png)

This project had been sitting in my mind for a while.
I wanted to create a board that was small, fairly powerful and had means of wireless communication.
This board ticks all of these needs.

![Assembled PCB without RF part.](/img/impulse/impulse-top-blink.jpg)

Assembled PCB without RF part.

***

## Some technical detais:
- uController - `STM32G431CBU6` (Cortex M4, 170Mhz);
- MPU - `BMI270`;
- Baro - `HP203B`;
- Wireless communication - `SX1268` (LoRa);
- Data logging & blackbox - 32Mb flash and SD card;
- GPIO - 6 regular pins and 4 high power;
- Expansion connector (SPI, I2C, UART, GPIO)
- Power - 3v3 and 5v0 buck regulators.
- Dimensions - 35mm x 50mm
- 8-layer board (6 layers probably could have been fine, but the price was the same ¯\\_(ツ)_/¯)

All CAD was done in KiCAD.

![Back side](/img/impulse/impulse-back.jpg)

***

## Final thoughts.
This board is still pretty much in development. All the hardware seems to be working,
so the next step is to write drivers for all of it. So don't get bored, continuation coming soon)

## Links:
- [Github repo](https://github.com/mariko357/impulse)
