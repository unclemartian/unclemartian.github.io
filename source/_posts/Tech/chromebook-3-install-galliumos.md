---
title: 【Tech】 Chromebook Tutorial 3 - Install GalliumOS
date: 2022-03-28 00:00:00
tags: ubuntu
---

# Overview

There are 2 ways to do a fresh installation of GalliumOS on Chromebook:

1. __Traditional Mode__ - replace ChromeOS entirely. Need a USD drive. 
1. __chrx Mode__ - install from ChromeOS command line. 

# Traditional installtion 

1. Go to __[chrome://system](chrome://system)__, and look for __hardware_class__. For my case it says "Akali" and "C5B-A4B-xxxxxxxx"

1. Go to https://wiki.galliumos.org/Hardware_Compatibility and check against your hardware class. I got __"Intel Kaby Lake"__.

1. Go to https://galliumos.org/download and download ISO of your version. 

1. Enabling Developer Mode (Esc+F3(refresh)+Power), and reboot.

1. Enable Legacy Mode booting.

    1. With your ChromeOS booted, press [Ctrl+Alt+T] and get a terminal ("crosh") window
    1. Run this: __'shell'__
    1. Then:

        sudo crossystem dev_boot_legacy=1

    1. If you have seen an error, simply skip and continue. (Reference: https://www.reddit.com/r/chrultrabook/comments/o9538s/trying_to_boot_from_usb_what_is_dev_boot_altfw_as/)

1. Disable WP (write protection). Check your device on [this MrChromebox](https://mrchromebox.tech/#devices) page to decide how you going to do it. In my case I use [the CR50 method](https://wiki.mrchromebox.tech/Firmware_Write_Protect#Hardware_Write_Protection)
    
    1. If you still not sure, check out this video: https://www.youtube.com/watch?v=EGZ6KfjEPP0

1. Check WP status, At crosh>

    sudo sh
    flashrom --wp-status


1. 

# chrx installation