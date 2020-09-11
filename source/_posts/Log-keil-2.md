---
title: "[Keil][02] - using CubeMX to generate the hardware setting code"
date: 2019-10-27 04:13:56
tags: [tutorial,log,stm,environment]
categories: 
- [porject-log]
- [tutorial]
- [keil]
- [stm]
---

Using the CubeMX to generate hardware setting code and put it on keil IDE with HAL library. 

___


# Get the software. #

https://www.st.com/en/development-tools/stm32cubemx.html

# Select the device that you are using #

Here I'm using the `NUCLEO-F103RB` deveopment board, so I can use the board selector to find my device.

![](https://i.imgur.com/OOZrXlu.png)

You can use the search function to search your board or make some conditions to find the board that suitable for you.

After you select the development board or chips that you want, it will show the features of the board. You can click the `Doc & Resources` and it will provide the data sheet and the references manual. You can download it, or you can find it on internet if you need.

After all, click the `Start Project` to start.
![](https://i.imgur.com/NQVUkNq.png)

# Do you settings. #

At this stage, you can just define the pins, set up the timer details, what prescaler using, what clock source are using etc. And you can click the Pin on the MCU, and it will show you what this pin can do. In the picture, we can see PA11 have many functions, but remember do not let two function using the same pin.

![](https://i.imgur.com/90Fiusd.png)

After setting up all the stuff, you can go to `project Manager` to create your project name, location. The most important part is choose the right `toolchain/IDE`, here the keil is `MDK-ARM` and the version you need to check you keil.

Then you can click the `GENERATE CODE` to create the keil project that already have all hardware setup code. 

![](https://i.imgur.com/0hNyTTG.png)

