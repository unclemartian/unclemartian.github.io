---
title: 【Tech】 Debian 9.9 on Wky
date: 2021-10-15 00:00:00
tags: ubuntu
---

# Debian 9

以 玩客云 硬件为例，测试使用 Debian 版的 Armbian 系统。

硬件信息如下：
     ____   ___   ___  ____
    / ___| ( _ ) / _ \| ___|
    \___ \ / _ \| | | |___ \
     ___) | (_) | |_| |___) |
    |____/ \___/ \___/|____/


    Welcome to ARMBIAN 5.88 user-built Debian GNU/Linux 9 (stretch) Mr-Li,QQ:691048250
    System load:   0.70 0.52 0.26  	Up time:       7 min
    Memory usage:  8 % of 996MB  	IP:            192.168.31.33
    Usage of /:    25% of 6.4G

Debian 9.9 （stretch）

    root@aml:~# lsb_release -a
    No LSB modules are available.
    Distributor ID:	Debian
    Description:	Debian GNU/Linux 9.9 (stretch)
    Release:	9.9
    Codename:	stretch

## Armbian installation

只要是将U盘烧好了“Armbian_5.88内置emmc需要U盘刷” 固件（1.5GB img file）。

然后插上wky，自动重装系统（不用刷inphic底包），很方便。

## Check 32 bit or 64 bit

    getconf LONG_BIT

## 修改系统时区

    armbian-config

#选择Personal
#选择Timezone
#选择Asia
#选择Shanghai
#然后依次选择 back exit 退出。

## 换源

    cd /etc/apt/
    vi sources.list

Content (note that Tsinghua and 163.com sources DO NOT WORK): 

    deb https://mirrors.ustc.edu.cn/debian/ stretch main contrib non-free
    deb-src https://mirrors.ustc.edu.cn/debian/ stretch main contrib non-free

    deb https://mirrors.ustc.edu.cn/debian/ stretch-updates main contrib non-free
    deb-src https://mirrors.ustc.edu.cn/debian/ stretch-updates main contrib non-free

    deb https://mirrors.ustc.edu.cn/debian/ stretch-backports main contrib non-free
    deb-src https://mirrors.ustc.edu.cn/debian/ stretch-backports main contrib non-free

    deb https://mirrors.ustc.edu.cn/debian-security/ stretch/updates main contrib non-free
    deb-src https://mirrors.ustc.edu.cn/debian-security/ stretch/updates main contrib non-free

### For docker

    https://mirrors.ustc.edu.cn/docker-ce

如果签名报错，运行这一行：

    sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys 公钥（例如648ACFD622F3D138）

就好了。

## Some useful apt to install 

    apt install python-setuptools
    apt install tmux
    apt install mosh

## Install Webmin

国外版的宝塔。

    /etc/apt/sources.list.d/
    vi webmin.list

内容：

    deb http://download.webmin.com/download/repository sarge contrib

然后：

    wget http://www.webmin.com/jcameron-key.asc --no-check-certificate
    apt-key add jcameron-key.asc
    apt update
    apt install webmin

然后就可以在 10000 端口查看 webmin 面板了。

# 自动同步 + 挂在U盘

## 挂载 U盘

TODO

一定不要修改 fstab。教训。

## 同步软件

1. resilio sync
1. syncthing

