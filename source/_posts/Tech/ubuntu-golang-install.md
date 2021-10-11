---
title: 【Tech】Install Golang on Ubuntu 20.04
date: 2021-09-03 00:00:00
tags: ubuntu
---

# Installation

First, download Golang.

Then:

    rm -rf /usr/local/go && tar -C /usr/local -xzf go1.17.linux-amd64.tar.gz
    ls /usr/local/go
    vi ~/.profile
    source ~/.profile 
    go version

