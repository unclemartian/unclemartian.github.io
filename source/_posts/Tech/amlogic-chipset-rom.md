---
title: 【Tech】 Amlogic 晶晨芯片刷机教程
date: 2021-11-03 09:00:00
tags: ubuntu
---

# 前言

晶晨(Amlogic)芯片有很多种设备。我玩过4种(只有前两者刷Armbian成功)：

1. Phicomm N1（S905）
1. Wankeyun（S805）
1. CM201-1 （S905L）
1. CM2000

其中每个设备都可以刷3种系统：

1. Android for TV
1. Armbian for Linux
1. Emuelec for gaming

# 结果

CM201-1 这个机器，启动Android一直没问题，但是无论换什么 dtb，armbian 都无法 boot。所以，就当电视盒子用吧。

CM2000 这个机器，不但无法刷 armbian，连Android底包都坏了。重刷之后可以使用TV box，但是无 Wifi。

wky是最容易刷的。

N1有个问题，就是Android底包经常被弄坏（同时armbian正常可用）。重刷一下 android 系统就好了。

> 为了刷n1，我弄坏了好几个u盘。而且好像最近买的这一批，只有32G可用于armbian，8G的一个都没成功。不知道为什么。

# N1刷机

## Android

对于 n1 盒子来说，使用这个Android底包就行：__斐讯盒子N1_YYFROM夏杰语音实用版__

http://www.yyfrom.com/cms/yyfrom/product/2021-7-3/166.html

刷机很简单。（需要去设备管理器种调整一下usb驱动，参考 https://post.smzdm.com/p/awkdzqvk/）

要注意2点：

1. Usb burning tool 软件中，先按“开始”，再连接 usb，否则 n1 连上直接就断开。
1. 一定要取消“擦除flash”和“擦除bootloader”。参考 https://post.smzdm.com/p/ax025099/

这个底包无法卸载 带广告的HDP。我用adb等进去，发现这个app装在 /system/app/ 里面了，不知道怎么卸载。算了。

