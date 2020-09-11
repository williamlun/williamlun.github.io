---
title: "[硬碟]驚嚇的收藏遺失事件"
date: 2019-10-12 08:43:35
tags: [log,hard disk,recovery,collection,data lost]
categories: 
- [porject-log]
- [Blog]
---

講一講大概係3年前發生既事, 係我第一次將programming學以致用的時刻, 對我黎講係一個幾深刻的事, 故事發生係由於電腦換底板的時候.

當時電腦的底板係 GIGABYPE 的 B75M, storage應該係1隻SSD, 1隻1TB hard disk, 再加一隻3 TB hard disk既.
好記得windows係做唔到直接read一隻3TB既MBR hard disk既, 係需要轉隻hard disk做GPT先read到. 
但係, 當我入手呢隻3TB hard disk 既時侯, GIGABYPE 既底板係有提供一個叫`unlock 3TB`既software, 而我當時冇研究, 直接用呢個software係MBR的format下直接用呢隻hard disk 而用到晒3TB.
問題就發生係換底板果陣喇, 我由GIGABYPE 轉投左去另一個品牌的底板, 冇左`unlock 3TB`我就頭都大埋, 一係放棄1TB, 一係轉做GPT. 咁我決定左轉做GPT啦, 但係果1TB的data...就...format左喇.

咁我就即刻搵解決方法啦, google `hard disk recovery`,搵下點樣救番d data. 然後用一個叫`Recuva`的software 做data recovery, 果程都還算順利 好多既收藏都成功救番, 救唔番的通常都係ass字幕為多.

救出黎既所有file都係變晒做number file. 但係scan果陣佢明明scan到原本個名. 真係比佢吹脹.

![當時的cap圖](https://i.imgur.com/HuHiIeX.jpg)

之後就有海量的無名file, 同一條file原本名稱的list出黎.

___

成千上萬的file, 無理由逐一改名架...100個file都做到傻喇. 咁我就決定寫個program去解決 第一次用program去解決實質需要.

兩條list的共通點就只有file size. 我寫左個java program read晒兩條list. 用file size做比對之後output番出黎. 

![當時的cap圖](https://i.imgur.com/M77bwwD.jpg)

最後都係用java 一次過跟住條list改名, 成功救番晒d data.