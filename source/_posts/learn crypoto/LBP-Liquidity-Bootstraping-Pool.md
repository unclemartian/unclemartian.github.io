---
title: LBP (Liquidity Bootstraping Pool)
date: 2021-02-25 06:58:58
tags: defi
---

# Balancer LBP

A __Balancer Liquidity Bootstrapping Pool__ is a tool designed to allow a project to generate liquidity from a smaller amount of seed capital than would normally be required. 

This is achieved through variable weighting of assets.

## Price adjustment

The liquidity guide pool also provides the project party with the ability to quickly adjust the weight, which can reduce the value of the tokens in the pool by adjusting the proportion of reserve assets, and prevent the eventual price surge due to early speculation. 

Under such a design mechanism, the opening price is usually deliberately set higher, and the lower price may appear in the later stage of the event.

So the users who want to participate in LBP need to pay attention to this risk, and when the project is popular enough, this risk will be reduced.

## Advantages

1. The price is relatively stable, not easy to lose control
2. Reduce the “front-running” of advanced trading bots and experts.
3. Some projects can support multiple tokens to participate in exchange

# Example: Mask token

在此次 LBP 活动启动时，我们将会投入共计 400 万个 $MASK 以及 80 万美元的 $USDC。起始售价为 $3.9。具体:

![](/images/lbp-balancer-mask.png)

注意：开盘价高，所有USDC都权重是95%，Mask的权重是5%。这样即节约了USDC，又发送出去了很多token份额。一石二鸟。

> An LBP allows projects to create meaningful liquidity and distribution at launch

LBP (Liquidity Bootstraping Pool) 为荷兰式拍卖，或称 “降价式拍卖”。其拍卖价格将由高到低依次递减，请大家在参与 LBP 前先详细了解它的运作方式，请在自己预期的价格范围内进行购买，切勿盲目 FOMO。Balancer LBP 能够通过改变预定的资金权重，在没有任何参与者购买的情况下，拍卖品会随着时间变长而降低价格。

![](/images/lbp-Exponential-Example-Pool-Weights.jpg)

## If you're swapping multiple tokens

the smart pool template allows for vectors of tokens and weights. So one option would be to start 80% XYZ, 10% DAI, 10% ETH and end at 33% XYZ, 33% DAI, 33% ETH. Allowing for users to purchase the project token in ETH or DAI.

# Reference

https://bitcointalk.org/index.php?topic=5319752.0
https://www.tuoluocaijing.cn/article/detail-10043661.html
https://medium.com/balancer-protocol/building-liquidity-into-token-distribution-a49d4286e0d4

## Balancer pool

https://pools.balancer.exchange/#/pool/0x1e6c8c4d3a9a6f633f28c70c7c80a412df42956a/about
