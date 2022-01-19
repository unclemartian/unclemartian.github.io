---
title: 【Tech】 How to mount shared folder for VirtualBox
date: 2022-01-10 00:00:00
tags: ubuntu
---

# Problem

Mount shared folders in VirtualBox.

## Install guest add-on

Run

	 cd /media/osboxes/VBox_GAs_6.1.28
	 sudo ./VBoxLinuxAdditions.run
	 sudo reboot

## config shared folder

一定要记得，这里输入“shared”。

![](/images/virtualbox-mount-shared-folder.png)

## Auto mount

如果没有自动加载，可以这样手动加载：

	  cd ~/Desktop/
	  mkdir shared-folder
	  sudo mount -t vboxsf shared ~/Desktop/shared-folder/

之后就行了。

如果权限出了问题，可以：

	sudo adduser $USER vboxsf
