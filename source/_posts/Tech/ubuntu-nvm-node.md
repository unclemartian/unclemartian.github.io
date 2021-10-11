---
title: 【Tech】Install Node/npm using Nvm
date: 2021-09-01 00:00:00
tags: ubuntu
---

# Install Node.js using nvm

## Use 'nvm' to manage node versions

1. Install nvm
    https://github.com/nvm-sh/nvm#install--update-script
    
2. Check current node versions

        nvm ls
        nvm ls-remote

3. Install node and npm

        nvm install v12

4. Use the following command

        nvm use 12

## Please Note

You may need to uninstall the system version node/npm, otherwise sudo have issues.

A pretty simple work-around would be:

    sudo vi ~/.bashrc

Content：

    alias node='$NVM_BIN/node'
    alias npm='$NVM_BIN/npm'
    alias sudo='sudo env PATH=$PATH:$NVM_BIN'

# Change node registry to taobao

    npm config get registry
    npm config set registry https://registry.npm.taobao.org/
    npm config set registry https://registry.npmjs.org/

## To check

    npm info underscore
    npm --registry https://registry.npm.taobao.org info underscore
    npm config get registry

# Useful npm packages

You might need to install these just in case you need them:

    npm install -g eslint yarn now truffle vue-cli hexo-cli
    npm install -g --force npx

To check your globally-installed packges:

    npm list -g --depth 0
