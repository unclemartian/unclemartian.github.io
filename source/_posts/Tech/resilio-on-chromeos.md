---
title: 【Tech】 Install Resilio Sync on Chromebook
date: 2022-03-25 00:00:00
tags: ubuntu
---

# Background

I only tested installed the Linux version. 

I did not test Android version, yet. 

# Steps


    echo "deb http://linux-packages.resilio.com/resilio-sync/deb resilio-sync non-free" | sudo tee /etc/apt/sources.list.d/resilio-sync.list
    
    curl -L https://linux-packages.resilio.com/resilio-sync/key.asc | sudo apt-key add

    (maybe optional) wget -qO - https://linux-packages.resilio.com/resilio-sync/key.asc | sudo apt-key add -

    sudo apt-get update
    
    sudo apt-get install -y resilio-sync

    sudo systemctl status resilio-sync
    
    sudo systemctl enable resilio-sync

    sudo systemctl status resilio-sync

So far so good. 

Test the link first: https://127.0.0.1:8888

Next step is to make the daemon accissible. First, check your username in ‘Crostini’ Linux.

```
whoami
```

Let's ensure that ‘normal’ user can read/write the synchronized files by 'rslsync' user. 

Run the following (mind the last command which [adding user permissions to the /home/rslsync folder](https://kenfavors.com/code/how-to-add-user-permissions-to-a-folder-in-ubuntu/))

    sudo usermod -aG [whoami] rslsync
    
    sudo usermod -aG rslsync [whoami]
    
    sudo chmod g+rw /home/rslsync/
    
    sudo apt install acl
    
    sudo setfacl -R -m "u:[whoami]:rwx" /home/rslsync

Done. 

# Reference 

https://www.davidfong.org/post/resiliosyncchromebook/
