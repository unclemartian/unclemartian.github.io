---
title: Hexo day-to-day best practise
date: 2000-01-01 13:58:00
tags: Hexo
---

# 关于代码管理

1. hexo blog 管理一切文字 + 图片内容，包括知识，技术和区块链内容
1. 一律使用 Github Pages + Travis Ci 管理发布
1. mindmap 使用私人飞书管理，不再参与同步，不上传 hexo
1. 不再使用 tiddlywiki，因为当文件 > 40MB 时，保存太慢

# 关于 tags，categories

1. Title prefix 写大类
1. 使用 tags 管理细类
1. 不使用 categories

## Rules

1. 每篇 post 都需要有 prefix，如 【Crypto】，【Tech】
1. 每个 prefix 都对应一些特定的 tags，比如 nft 对应【Crypto】

__具体安排如下__

* 【Crypto】
    * tags: nft
    * tags: defi
    * tags: crypto people
* 【Tech】
    * tags: ubuntu
    * tags: technology
* 【Read】
    * tags: arts
    * tags: books
    * tags: knowledge

# Hexo day-to-day

## 语法

https://www.markdownguide.org/basic-syntax/

## 发布

Hexo 发布流程如下：

1. 保证 Sync 成功
1. 运行：git push origin hexo-source 
1. hexo generate is not required
