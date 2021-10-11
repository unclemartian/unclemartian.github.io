---
title: 【Crypto】Loot master wiki
date: 2021-09-29 00:00:00
tags: crypto
---

# Loot

Loot 是由 Dom Hofmann 发起、靠社区推动的一个 NFT 项目。

上线于2021年8月27日。

https://etherscan.io/address/0xff9c1b15b16263c61d017ee9f65c50e4ae0113d7

> Dom Hofmann, 视频共享应用程序 Vine 的联合创始人

每一枚 Loot 代表一组具有随机稀缺特性的冒险装备

1. upper body
  1. 武器（Weapons）
  1. 头甲（Head Armor）
  1. 胸甲（Chest Armor）
1. lower body
  1. 腰甲（Waist Armor）
  1. 手甲（Hand Armor）
  1. 脚甲（Foot Armor）
1. accessory
  1. 项链（Necklaces）
  1. 戒指（Rings）

# 特性

元数据无法修改：这对艺术收藏品 NFT 而言是理想情况

Loot：通过可组合性、互操作性提供更多体验的 NFT

将艺术层从信息层剥离，只保留必要的文本内容。有点类似 Ubuntu 和 Linux kernel 的关系。

已经有很多评论指出 Loot 是从 JPG 到 TXT 的一次呈现形式的创新。如果深入挖掘，会发现这其实是一种链上内容表达模式的新实验，以及程序化生成技术在艺术收藏品 NFT 以外的应用实例。而更进一步地，Dom 还在程序化生成技术中引入了社交随机性元素，并开辟出一条自下而上的发展新路径。

## before Loot

大部分 NFT 声明所有权的对象是通过哈希算法锁定的一个 JPG 文件：发行方将 JPG 数据映射成一串哈希指纹用于完整性校验，将该哈希指纹、储存 JPG 文件的路径与内容描述、发行信息、创作者签名等信息构成元数据；元数据也不一定直接保存在区块链上，而是将储存元数据的路径再次以哈希摘要的形式上传至区块链

![](/images/loot-before-loot.jpeg)

问题

元数据与所有权声明分离可能导致数据可用性和数据完整性问题；如果把原始图像全都上链，又会占用本就稀缺的公共资源，后期维护成本也很高。

以图片形式呈现的元数据后期无法修改，这对艺术收藏品 NFT 而言是理想情况，而对想要通过可组合性、互操作性提供更多体验的 NFT 来说是一个潜在问题，比如 IP 的进化、游戏道具的升级。目前在 Axie Infinity 等游戏中通过「孵化」生成一个新的 NFT 来达到这一目的。

## after Loot

将 UI 层从信息内核剥离，只保留必要的文本内容。

![](/images/loot-after-loot.jpeg)

# procedural generation

Crypto Punks 的项目方 Larva Labs 也率先开发了此类产品 Autoglyphs

曾经不知名的链上生成类艺术品 NFT 培育平台 Art Blocks 已然实现周交易量排名第 5

> Art Blocks 是一个邀请制艺术家培育平台，为艺术家提供了程序化生成算法的创作平台。培育出的作品集对应的生成算法脚本（例如 p5js）将作为一个 project 储存于以太坊智能合约。收藏家可根据作品风格挑选 project
