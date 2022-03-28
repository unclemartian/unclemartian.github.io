---
title: 【Tech】 Chromebook Tutorial 4 - GalliumOS
date: 2022-03-28 00:00:00
tags: ubuntu
---

# Overview 

__GalliumOS__ is built solely for Chromebooks.

https://wiki.galliumos.org/Welcome_to_the_GalliumOS_Wiki

这个 Linux 系统是基于 Ubuntu 18.04 (bionic) 的。

# 换源 Change source

## Before Everything

Give yourself __‘su’__ previlege! 

在 Users Settings 中，把 Account Type 改为 Administrator. 

不换源的话，language 和 fcitx 安装会出问题。

    cd /etc/apt/
    vi sources.list

The aliyun source:

    deb http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse
    deb-src http://mirrors.aliyun.com/ubuntu/ bionic main restricted universe multiverse

    deb http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse
    deb-src http://mirrors.aliyun.com/ubuntu/ bionic-security main restricted universe multiverse

    deb http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse
    deb-src http://mirrors.aliyun.com/ubuntu/ bionic-updates main restricted universe multiverse

    deb http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse
    deb-src http://mirrors.aliyun.com/ubuntu/ bionic-proposed main restricted universe multiverse

    deb http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse
    deb-src http://mirrors.aliyun.com/ubuntu/ bionic-backports main restricted universe multiverse

# Install fcitx

首先，下载搜狗：

https://pinyin.sogou.com/linux/help.php

Go to "Language Support" 或者“语言支持”，添加“中文”，并且把输入法设置成：fcitx。

![](/images/galliumsos-fcitx-sogoupinyin.png)

然后：

    sudo dpkg -i sogoupinyin_2.4.0.3469_amd64.deb

# Install Chrome, VSCode

Just download and install:

1. https://www.google.cn/chrome/
1. https://code.visualstudio.com/
