---
title: 【Tech】 Chromebook Tutorial - GalliumOS
date: 2022-03-28 00:00:00
tags: ubuntu
---

# Overview 

__GalliumOS__ is built solely for Chromebooks.

https://wiki.galliumos.org/Welcome_to_the_GalliumOS_Wiki

这个 Linux 系统是基于 Ubuntu 18.04 (bionic) 的。

# Before Everything

## Give yourself ‘su’ previlege

在 Users Settings 中，把 Account Type 改为 Administrator。

## 换源 Change apt source 

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

## Install fcitx

首先，下载搜狗：

https://pinyin.sogou.com/linux/help.php

Go to "Language Support" 或者“语言支持”，添加“中文”，并且把输入法设置成：fcitx。

![](/images/galliumsos-fcitx-sogoupinyin.png)

然后：

    sudo dpkg -i sogoupinyin_2.4.0.3469_amd64.deb

# Install Softwares

## Install Chrome, VSCode

Just download and install:

1. https://www.google.cn/chrome/
1. https://code.visualstudio.com/

# Install Node.js

Please refer to: https://unclemartian.github.io/2021/09/01/Tech/ubuntu-nvm-node/

# Install Resilio Sync

    sudo systemctl status resilio-sync
    sudo systemctl enable resilio-sync
    sudo systemctl start resilio-sync

Check: https://127.0.0.1:8888/gui/

To config permission: https://unclemartian.github.io/2021/08/13/Tech/ubuntu-system-commands/
