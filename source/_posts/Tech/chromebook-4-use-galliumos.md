---
title: 【Tech】 Chromebook Tutorial 4 - Using GalliumOS
date: 2022-03-29 00:00:00
tags: ubuntu
---

# Overview 

__[GalliumOS](https://wiki.galliumos.org/Welcome_to_the_GalliumOS_Wiki)__ is built solely for Chromebooks.

这个 Linux 系统是基于 Ubuntu 18.04 (bionic) 的。

# Basics

## Before Everything

Give yourself __‘su’__ previlege! 

在 Users Settings 中，把 Account Type 改为 Administrator. 

不换源的话，language 和 fcitx 安装会出问题。

![](/images/TODO.png)

# 换源 Change source

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

https://pinyin.sogou.com/linux/

Go to "Language Support" 或者“语言支持”，添加“中文”，并且把输入法设置成：fcitx。

![](/images/galliumos-fcitx-sogoupinyin.png)

然后：

    sudo dpkg -i sogoupinyin_2.4.0.3469_amd64.deb

如果缺依赖，就：

    sudo apt -f install

这时候仍然可能会失败，报以下错：__installing sogoupinyin would break fcitx-ui-qimpanel__。这个原因是[搜狗拼音安装包中含有fcitx-ui-qimpanel，与系统已有的fcitx-ui-qimpanel产生了冲突](https://www.bbsmax.com/A/MyJxmX4p5n/)，所以，删除 fcitx-ui-qimpanel。

    sudo apt-get remove fcitx-ui-qimpanel

后来，再安装sogou，或者先安sogou后安locale包，再重启机器，总之就好了。版本号：搜狗个人版 4.0.0.1605 （2022年3月）。

# Install Chrome, VSCode

Just download and install:

1. https://www.google.cn/chrome/
1. https://code.visualstudio.com/

## Othere important software

Required to build some packages: 

    sudo apt-get install pkg-config
