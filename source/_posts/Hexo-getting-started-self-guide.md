---
title: Hexo getting started self guide
date: 2099-09-09 13:58:00
tags:
---

# Background 

Build on Node.js, Hexo is a much more user-friendly blogging platform compared to Jekyll or Octopress. However, setting up the source/public branch and Github Pages may not be so straight-forward.

Here is my personal guide. I refer the the steps below: 

![](/images/hexo-setup-guide-overview.png)

## Setup up hexo locally

    npm install hexo-cli -g
    hexo init unclemartian-blog
    cd unclemartian-blog/
    npm i // npm install
    hexo g // generate
    hexo s // serve

Now Hexo runs locally. 

## Upload to GitHub

Now you can 'git init' and change your github config email and username, if you want to.

Make sure public/ is gitignore-ed but the theme/ folder is not: 

    .DS_Store
    Thumbs.db
    db.json
    *.log
    node_modules/
    public/
    .deploy*/
    debug.log

Then create a repo named unclemartian.github.io

    git checkout -B hexo-source
    git remote add origin git@github.com:unclemartian/unclemartian.github.io.git
    git push -u origin hexo-source

Now your Github should have hexo code under __hexo-source__ branch.

## Setup Travis CI

Travis CI is a continuous integration & continuous delivery platform. 

1. Add Travis CI to your account.
    https://github.com/marketplace/travis-ci
    
1. Go to Applications settings, configure Travis CI to have access to the repo.
    https://github.com/settings/installations
    
1. On Github, generate a new token with repo scopes. Note down the token value.
    https://github.com/settings/tokens
    
1. On Travis page, go to your repo’s setting. Under __Environment Variables__, put __GH_TOKEN__ as name and paste the token onto value. Click __Add__.
    https://travis-ci.com/github/unclemartian/unclemartian.github.io/settings

## Public to master

It is required that GitHub Pages __MUST__ publish the (content of) public folder on __master branch__.

Create .travis.yml in hexo folder (alongside _config.yml & package.json).

    sudo: false
    language: node_js
    node_js:
      - 10 # use nodejs v10 LTS
    cache: npm
    branches:
      only:
        - hexo-source # build master branch only
    script:
      - hexo generate # generate static files
    deploy:
      provider: pages
      skip-cleanup: true
      github-token: $GH_TOKEN
      keep-history: true
      target_branch: master # generate static files to master
      on:
        branch: hexo-source
      local-dir: public

Commit to Github, and Travis CI should start automatically. 

Once it's complete, I can checkout the published blog at: https://unclemartian.github.io/
