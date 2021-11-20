---
title: 【Crypto】 Rarity Calculation Methods
date: 2021-11-18 00:00:00
tags: crypto
---

# Why

__rarity__ is one of the most important factors in determining the value of an individual NFT.

On Opensea, each NFT have traits: 

![](/images/nft-calculate-rarity-1.png)

## Rarity 计算方法

1. Trait Rarity Ranking 单一属性法
    只选最 rare 的 traits，值越小越好。忽略其他一切 traits。
    
1. Average Trait Rarity 平均数法
    所有 traits 权重相等，计算出平均值。

1. Statistical Rarity 乘积法
    所有 rarity 值的乘积 （但是有的 nft 缺少某些 traits，比如 22.56% 的 ape 不戴帽子）

1. Rarity score 商值法
    用除法计算所有 traits 的分数，最终返回sum。

以下具体说明。

# 1 Trait Rarity Ranking

Simply comparing the rarest trait of each NFT（只选最小值），例如：

1. Ape #73 s rarest trait is Sold Gold Fur which 0.46% have
1. Ape #9941's rarest trait is Bored Unshaven Dagger which 0.28% have
1. Ape #9542’s rarest trait is Bored Unshaven Pizza which 0.26% have

## weakness

It doesn’t look at the overall rarity of the NFTs at all, just the rarest trait.

# 2 Average Trait Rarity

Averaging the rarity of traits that exist on the NFT.

![](/images/nft-calculate-rarity-2.png)

以上的例子如果按照 trait rairty ranking，NFT 1 是最 rare 的，因为 rarity = 10%

但按照 average trait，那么显然 NFT 2 更 rare。

## weakness

It puts too much weight on the overall rarity of every trait, but NFTs with single super rare trait are not valued enough.

Their rarity value gets too ‘diluted’ by the other traits.

# 3 Statistical Rarity

This become a somewhat popular method and is used very often in community made spreadsheets.

It was first [mentioned by Adam Chekroud](https://achekroud.substack.com/p/d8f13e0a-ae26-40e4-bff2-beacb2916ff0). 

Basically: calculate the overall rarity of an NFT by multiplying all of it’s trait rarities together.

![](/images/nft-calculate-rarity-3.png)

1. Ape #73’s statistical rarity is 0.00000000070744%
1. Ape #9941’s statistical rarity is 0.00000056965722%
1. Ape #9542’s statistical rarity is 0.00000044983967%

# 4 Rarity Score

这是个比较特别的计算方法。

> [Rarity Score for a Trait Value] = 1 / ([Number of Items with that Trait Value] / [Total Number of Items in Collection])

然后所有 traits 的 rarity score 相加，等于最终的 rarity score。

> The total Rarity Score for an NFT is the sum of the Rarity Score of all of it’s trait values.

例如：Punk中只有9个 Alien，那么 Punk Type 这一项的 rarity score 就是 10,000 / 9 = 1111

Punk中有24个 Ape，那么 Punk Type 这一项的 rarity score 就是 10,000 / 24 = 417

![](/images/nft-calculate-rarity-4.png)
*https://rarity.tools/cryptopunks/view/7804*

## Advantage

Rarity Score 的好处是，不但考虑了所有的 traits，而且对于某些非常 rare 的 traits，有很好的突出的效果。

# 总结

Trait Rarity Ranking 只考虑单一的 traits，略显不平衡。

Average Rarity，Statistical Rarity 又比较容易稀释那些特别稀有的 traits，例如 Alien Punk。

我觉得 Rarity Score 最好。用作者的原话讲：

> Rarity Score give results that give enough emphasis to __single rare traits__ and also includes __overall trait rarities__ in its calculation. 

> And most importantly the results it gives match better with our human expectations.

# Reference

https://raritytools.medium.com/ranking-rarity-understanding-rarity-calculation-methods-86ceaeb9b98c
