---
title: 【Tech】 Amlogic 晶晨芯片刷机教程
date: 2021-11-03 09:00:00
tags: ubuntu
---

# 前言

晶晨(Amlogic)芯片有很多种设备。我玩过4种(只有前两者刷Armbian成功)：

1. __Phicomm N1__（S905D / 2G）
1. __玩客云__（S805 / 1G）
1. CM201-1 魔百盒（S905L / 1G）
1. CM2000 红

其中每个设备都可以刷3种系统：

1. Android for TV
1. Armbian for Linux
1. Emuelec for gaming

# 结果

CM201-1 魔百盒这个机器，启动 Armbian 一直没问题，但是无论换什么 dtb，Armbian 都无法 boot。所以，就当电视盒子吧，还挺好用的。

> 这个帖子提到一个奇淫巧技，不知道能不能用，摘抄如下：
> 
> 使用adb shell reboot update发现启动失败，多次尝试也是如此。
> 
> 。。。受到启发，把启动盘根目录下的aml_autoscript.zip改名为update.zip,输入adb shell reboot update命令后直接引导进入armbian
> 
> https://blog.csdn.net/u012481946/article/details/113774089

CM2000 这个机器，不但无法刷 Armbian，连Android底包都坏了。重刷之后可以使用TV box 功能，但是无 Wifi，插线用。

wky是最容易刷的。我在其中一个上面装了 Armbian 跑同步盘，十分稳定。

N1有个问题，就是Android底包经常被弄坏（Armbian正常可启动）。只要重刷一下 Android 系统就好了。

> 为了刷n1，我弄坏了好几个u盘。而且好像最近买的这一批，只有32G可用于 Armbian，8G的一个都没成功。不知道为什么。

# N1刷机

## Android

对于 n1 盒子来说，使用这个Android底包就行：__斐讯盒子N1_YYFROM夏杰语音实用版__

http://www.yyfrom.com/cms/yyfrom/product/2021-7-3/166.html

刷机很简单。（需要去设备管理器种调整一下usb驱动，参考 https://post.smzdm.com/p/awkdzqvk/）

要注意2点：

1. Usb burning tool 软件中，先按“开始”，再连接 usb，否则 n1 连上直接就断开。
1. 一定要取消“擦除flash”和“擦除bootloader”。参考 https://post.smzdm.com/p/ax025099/

这个底包无法卸载 带广告的HDP。我用adb等进去，发现这个app装在 /system/app/ 里面了，不知道怎么卸载。算了。

![](/images/usb-burning-tool-n1.jpg)

参考：https://post.smzdm.com/p/a25gpgx7/

## EmuElec

Emuelec(xxxELEC之类的系统)与Armbian不兼容，启动过ELEC就启动不了Armbian了，反之可以。

所以ELEC对boot环境具有破坏性，只能想办法恢复原来的boot环境，重新刷机可以解决。

刷机过程，参考这里：

https://www.cnblogs.com/milton/p/11883811.html

## Armbian

Armbian 经常把 Android系统搞坏。哎。

另外，试用了桌面版的 Debian 9，实在是没什么可用性，而且有时候无法自动连接 Wifi。不建议玩儿。

最佳的固件就是 5.77版本的 Debian stretch。

5.99 / 20.10 版本我没成功过。

# WKY刷机
