---
title: 【Crypto】 Loot master wiki
date: 2021-09-29 00:00:00
tags: crypto
---

# Loot Intro

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

# 特点总结

表面：NFT 从 JPG 到 TXT 的一次__呈现形式__的创新。

深层：往后看。

## Before Loot

### NFT所有权 --> 通过 hash value 锁定的一个 JPG 文件

![](/images/loot-before-loot.jpeg)

具体操作：

1. 发行方将 JPG 数据映射成一串 signature (哈希指纹) 用于完整性校验。例如 https://gateway.pinata.cloud/ipfs/QmUnRSRJF7JWViesqHTiNSSpeRCEj5AND58jqDghAbPG2b

1. 将该 ipfs signature、文件路径与内容描述、发行信息、创作者签名等信息构成 Metadata (元数据)。例如 https://metadata.theunstablehorsesyard.com/horse/32

  ```
  Metadata：
  {"image":"https://gateway.pinata.cloud/ipfs/QmUnRSRJF7JWViesqHTiNSSpeRCEj5AND58jqDghAbPG2b","description":"The Unstable Horses Yard are unique collectibles, with provably randomized traits and physical attributes. Own, trade, and play in the 3D world with your unique horse.","attributes":[{"trait_type":"hoof","value":"Paper"},{"trait_type":"clothes","value":"Muskateer"},{"trait_type":"ear","value":"Earrings"},{"trait_type":"eyes expression","value":"Unstable"},{"trait_type":"eyes","value":"Monocle"},{"trait_type":"neck","value":"Love Necklace"},{"trait_type":"mane","value":"Blonde"},{"trait_type":"mouth expression","value":"Closed Mouth"},{"trait_type":"mouth","value":"Cigarette"},{"trait_type":"hat","value":"Ribbon"},{"trait_type":"breed","value":"Zebra Cross"},{"trait_type":"Generation","value":1,"display_type":"number"},{"trait_type":"Stamina","value":98,"max_value":100},{"trait_type":"Strength","value":86,"max_value":100},{"trait_type":"Natural Speed","value":77,"max_value":100},{"trait_type":"Adaptibility","value":99,"max_value":100},{"trait_type":"Pedigree","value":90,"max_value":100},{"trait_type":"Instability","value":60,"max_value":100},{"trait_type":"Alertness","value":80,"max_value":100}]}
  ```

1. Metadata 很长，通常不存在链上，而是将储存 Metadata 的路径再次以哈希摘要的形式上传至区块链。

  1. 参考上述例子，这个链接最终存在了链上： https://metadata.theunstablehorsesyard.com/horse/32 （合约地址： https://etherscan.io/address/0x0e4245ccb9954ead73f8bab13607cd2d86efc84c#readContract）
  1. 更好的办法是，存在 IPFS上，这样数据安全性更靠谱一点。

### 问题

metadata 和 ownership 是分离的

1. 可能导致数据可用性和数据完整性问题
1. 如果把原始图像全都上链，又会占用本就稀缺的公共资源
1. 上面那个例子更为甚者，中心化网站可以直接修改 metadata 内容。

### 进一步问题

IP 的进化、游戏道具的升级，无法解决。

> 目前在 Axie Infinity 等游戏中通过「孵化」__生成一个新的 NFT__ 来达到这一目的。

## After Loot

将 NFT 的“art”层从“information”层剥离，只保留txt。有点类似 Ubuntu 和 Linux kernel 的关系。

1. 可组合性、互操作性，更多元体验；
1. 程序化生成技术 (GenArt) 中引入了__社交随机性__元素。

![](/images/loot-after-loot.jpeg)

# Generative art

又称：__程序化生成（procedural generation）__

Loot 是程序化生成（procedural generation）的一种实例。

Crypto Punks 的项目方 Larva Labs 也率先开发了此类产品 Autoglyphs。

曾经不知名的链上生成类艺术品 NFT 培育平台 Art Blocks 已然实现周交易量排名第 5

> Art Blocks 是一个邀请制艺术家培育平台，为艺术家提供了程序化生成算法的创作平台。培育出的作品集对应的生成算法脚本（例如 p5js）将作为一个 project 储存于以太坊智能合约。
> 收藏家可根据作品风格挑选 project，购买的 NFT 将根据内置随机种子产生一组随机变量，该变量控制生成算法生成一幅符合该风格的作品，不限于 静态图像、 3D 模型 或 可交互的体验（鼠标互动）。

# Reference

https://www.chainnews.com/articles/908208201053.htm?
https://medium.com/treum_io/on-chain-artwork-nfts-f0556653c9f3
