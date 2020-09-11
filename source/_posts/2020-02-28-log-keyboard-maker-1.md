---
title: "[keyboard][00] - 記錄個自製鍵盤的計劃"
date: 2020-02-28 04:37:38
tags: [log, keyboard, STM, AVR, RGB, wireless]
categories: 
- [porject-log]
- [Blog]
---

作為一個電子仔, keyboard mouse USB呢d咁平常見到既野都唔識整好似有d講唔過去.
不過電子呢科本身讀緊既野就係100年前既科技, 仲要100年前d野都已經讀到成班死死下. 
21粒transisor組成741讀一個sem, 但係用緊既CPU GPU上十億粒.
keyboard mouse呢d近2,30年先有既野我唔識整都唔出奇呀. 
已經冇野驚, 讀電子既人就係咁廢咁old school. 我就係讀電子,我就爛.
所以今次試下整個keyboard出黎玩下先.
___

## 階段計劃 

<b> 第一階段 一般有線鍵盤</b>

就係你係d電腦鋪, 垃圾咁放一箱係到賣10蚊20蚊既垃圾一般有線鍵盤.
雖然話技術上係垃圾 但係我諗住用機械軸 所以都叫做係機械鍵盤既.

<b> 第二階段 無衝有線鍵盤 with RGB</b>

一個keyboard, 如果有個制同另一個唔可以同時撳既話. 佢係一個失敗既keyboard. 
同時間又有幾多個key可以一齊撳 亦係一個問題. 所以無衝非常重要.
RGB唔洗講啦, keyboard身價直接上升幾百蚊.((成本都貴左


<b> 第三階段 無線鍵盤 with RGB </b>

RGB科技樹係上個階段解鎖左相信可以直接黎到無線keyboard既階段. 
呢個階段難度極高. 相信一定會卡係呢到.


<b> 最後階段 可有可無線鍵盤</b>

插線就有線 唔插就無線 仲要RGB 市場上係有呢d產品 千幾2千銀lo.

___

28/2/2020

## 第一階段計劃

<b>plan A - STM32F103 or F446 with keyboard array</b>


好處: 
    使用的硬件最為熟悉 對develop environment幾熟 
    單粒解決所有問題
壞處:
    個USB HID lib我仲未睇得明
    software上最接近底層 debug時間預計最長


<b>plan B - ATmega32U4 with keyboard array</b>


好處: 
    同樣單粒解決所有問題
    software上預計比STM high level 預計較易
壞處:
    AVR好耐冇用唔記得晒 
    chip level programmer都冇 唔知點入手
    8-bit controller硬係好似差咁d


<b>plan C - keyobard IC</b>


CH9328 - serial to keyboard HID chip (直接無線都得lu)
usb鍵盤模塊 - 之前買過玩過

好處: 
    簡單 方便 快捷 一定得
壞處:
    咁我玩黎做咩 不如直接買keyboard
    鍵盤模塊既話 PCB design唔到 因為會係咁既樣

![Imgur](https://i.imgur.com/VzuzjIf.png)

結: 暫時試下planA先 搞唔掂先算



29/2/2020

簡單update下

一開始係到睇用咩chip黎做keyboard, 之後發現其寅係USB HID standard下用咩都係差唔多
都係砌好個USB report descriptor 同埋個report之後send出去 只要做到呢個function就得
睇下睇下覺得基本上跟住d網上TUT做呢 個第一階段應該就KO到 所以先用prototype完成第一階段既技術問題先
但當然rescarch階睇多d就更好啦 之後就發現問題幾多 
CAPS LOCK state點收 完全唔知....
睇下睇下順便睇下無衝keyboard HA!

原來HID stardand 係 USB 上面, 而HID keyoboard一早寫死左只可以send 6個key
今次開心喇 基本上個科技樹點錯左 NKRO keyboard 同hid keyobard係兩回事
初步明白一個USB device既建立 問題係HID keyboard 同NKRO keyboard應該點樣係同一個keyboard共存.


16/3/2020

過咗半個月，科技樹解鎖到第二階段。我今次使用既策略係一步登天，因為成本實在太高了。
如果我每一個階段都做一次PCB做一次tseting呢, 唔計fail起碼做四次，但其實每次都只係有少少改動，銀包實在唔容許呢件事。所以只有大改既時侯先會出product.
另外，RGB呢個科技樹好似唔係想像中咁易，最大既問題係power.
諗一諗USB port 最大power都只係5V 500mA，即係2.5W 如果係87key keyboard 加埋3粒狀態燈，有90粒led。咁當然500mA唔會拎黎計數啦，拎個2/3 330mA黎計。
再經過隨便估算
![隨便估算](https://i.imgur.com/HcIsDRO.png)
MCU max用30mA，300mA分比90粒led，加埋d power lost，每粒3mA左右應該都夠。但係唔好唔記得一粒RGB led = 3粒led, 即係每粒得1mA。個光度就同5V drive led 加 5k ohm一樣。相信只能夠加d scanning去減少power了。 更唔洗提無線d 電會點chur.

所以RGB做後少少啦 做左無線先。
現時科技樹:
一般有線鍵盤 ok
無衝有線鍵盤 ok
RGB suspend
無線鍵盤 processing
