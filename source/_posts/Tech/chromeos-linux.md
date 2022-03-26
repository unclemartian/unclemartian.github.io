---
title: 【Tech】 ChromeOS tutorial - Linux
date: 2022-03-26 00:00:00
tags: ubuntu
---

# Change apt source 

First, check the OS vesion

    ngu@penguin:~$ cat /etc/os-release 
    PRETTY_NAME="Debian GNU/Linux 11 (bullseye)"
    NAME="Debian GNU/Linux"
    VERSION_ID="11"
    VERSION="11 (bullseye)"
    VERSION_CODENAME=bullseye
    ID=debian
    HOME_URL="https://www.debian.org/"
    SUPPORT_URL="https://www.debian.org/support"
    BUG_REPORT_URL="https://bugs.debian.org/"

We now know that ChromeOS 99 have __Debian 11 (bullseye)__ installed by default (as of March 2022).

TODO

# Install VSCode

    sudo apt-get update
    sudo apt-get install -y gnome-keyring

Then [download the deb](https://code.visualstudio.com/download) and double click to install.

# Install Node.js

Please refer to: https://unclemartian.github.io/2021/09/01/Tech/ubuntu-nvm-node/

# Install Resilio Sync

Please refer to: TODO
