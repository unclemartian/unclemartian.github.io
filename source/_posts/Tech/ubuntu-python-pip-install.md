---
title: 【Tech】Install Python/pip on Ubuntu 20.04
date: 2021-09-04 00:00:00
tags: ubuntu
---

# Installation

Replace python2 with python3: 

    python --version 
    sudo apt install software-properties-common
    sudo add-apt-repository ppa:deadsnakes/ppa
    sudo apt update
    sudo apt install python3.8
    python --version 
    which python3
    sudo apt install python-is-python3

To install pip on python3:

    python --version 
    pip
    pip3
    sudo apt install python3-pip
    pip
    pip --version 

Now you have python3 and pip installed on Ubuntu. 
