---
title: "[keyboard][01] - 自製鍵盤計劃"
date: 2020-04-27 00:47:51
tags: [log, keyboard, STM, AVR, RGB, wireless]
categories: 
- [porject-log]
- [Blog]
---

經過一段時間research 個科技樹基本上生到7788
基本上只係差RGB就可以完成整個keyboard
咁呢篇blog主題就係記低番點樣整出黎 就廢事唔記得
小弟畢業做左廢青幾個月 終於就搵到工
所以應該唔會有咁多時間精力去做呢d自發project 
其實對未來都仲係好迷茫 遲d開篇blog講下近況啦
___

## 設計初衷
`````````
其實本身我個keyboard就係張檯幾入既位置
如果我挨後既話 隻手要伸到勁遠先打到字
所以想有個wireless keyboard可以比我挨後果陣用
但係平時係以有線方式為主
同時亦可以有雙device共用一隻keyboard既構想
所以基本上只可以自己整


## HID device

一個HID 或者USB device其實係由一個`HID Report Descriptor` 去定義的
因為HID devier種類好多 而每一個device既input都唔一樣 
好似Keyboard 都有分full size既104key keyboard 冇keypad既 87key keyboard 
仲有股票買賣果d得數字keypad既keyboard 咁呢d全部都係keyboard 但已經有極多種類
然後mouse 耳機 keyboard+mouse pad 等等等等 好多既device

所以每一個deivce都有一個Report Descriptor 去define 呢一個deivce既input同output
從而令OS知道呢一個deivce的input係咩output係咩
而以下呢兩份就係USB官方document講 HID Report Descriptor點寫既
[https://usb.org/sites/default/files/hid1_11.pdf](https://usb.org/sites/default/files/hid1_11.pdf)
[https://www.usb.org/sites/default/files/documents/hut1_12v2.pdf](https://www.usb.org/sites/default/files/documents/hut1_12v2.pdf)

坦白講就咁睇呢份野就識寫係我呢d level係冇乜可能既
所以就會夾埋d其他教學一齊睇既 
好在HID係d 10幾20年前既產物 相關資源非常多 大家可以自己搵下
咁我就覺得呢個兩網就講得幾清楚
[https://eleccelerator.com/tutorial-about-usb-hid-report-descriptors/](https://eleccelerator.com/tutorial-about-usb-hid-report-descriptors/)
[http://joinmaker.blogspot.com/2019/11/usb-hid-3.html](http://joinmaker.blogspot.com/2019/11/usb-hid-3.html)

咁就可以用Report Descriptor 創造一個自已獨有的HID device喇