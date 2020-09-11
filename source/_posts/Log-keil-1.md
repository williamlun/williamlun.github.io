---
title: "[Keil][01] - Setting up the environment to use keil IDE"
date: 2019-10-26 04:59:29
tags: [tutorial,log,stm,environment]
categories: 
- [porject-log]
- [tutorial]
- [keil]
- [stm]
---

    Setting up the keil IDE to program STM32 development board.
___


# Get the software. #

https://www.keil.com/download/product/

download the `MDK-arm`. which is the development environment for Cortex and Arm devices.

install the environment. 

# PackInstaller #

After installing the software, you will open up a packinstaller automatically.
if not you can open keil uVision and open the packInstaller by click the icon.

![Imgur](https://i.imgur.com/hqeBKO0.png)

In the pack installer, you can find the chip or development board on the right easily by using the search function.

Here I'm using the NUCLEO-F103RB development board, and the board is using the STM32F103RB chip.

![Imgur](https://i.imgur.com/b3KUTbk.png)

On the left, you have so many packs are able to install. If you are new on this, just make sure you have these.

![Imgur](https://i.imgur.com/dt4Co1u.png)

# Copy an example code. #

If you are using the NUCLEO-F103RB development board like me, you can copy an example code.

![](https://i.imgur.com/Q2ls7GJ.png)

After copy the example, the keil will open automatically, and you can open the `Blinky.c` find the `main` and it will look like this.

![](https://i.imgur.com/MWLzIxk.png)
