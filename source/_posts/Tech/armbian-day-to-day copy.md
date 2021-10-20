---
title: 【Tech】 Armbian day to day 使用教程
date: 2021-10-19 09:00:00
tags: ubuntu
---

# SSH 登陆

    export LC_ALL="en_US.UTF-8" && mosh root@192.168.123.215
    a***

## Tmux 

    tmux ls
    tmux attach -t 0 (or simply tmux attach)
    tmux detach -a

To detach current: 

    Ctrl + b, then ‘d'

# 控制台和应用

Webmin 在 10,000 端口。

https://192.168.123.215:10000

    wky
    a***

## Resilio 同步

https://192.168.123.215:8888/gui/

    wky
    a***

## Syncthing

https://192.168.123.215:8384

    wky
    a***

