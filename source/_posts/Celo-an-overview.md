---
title: Celo, an Overview
date: 2020-04-07 13:04:48
tags:
---

# Motivation 

1. lower costs 
1. 24/7 global access

However，

1. crypto-assets are __volatile__
1. long hexadecimal cryptographic addresses

# Celo Intro

1. Lightweight identity
1. Stability mechanism
1. Incentives and governance for sustainability

based off Ethereum. Include：

1. a native digital asset called Celo Gold
1. all Celo assets 

## 1 - Lightweight identity

Address-based Encryption (a variant of “identity-based encryption”)

Attaching phone numbers to Celo addresses enables capturing reputation (EigenTrust)

## 2 - Stability mechanism

50% of cGLD will go to the reserve and 50% of cGLD will be used to buy crypto-assets (e.g. Bitcoin and Ether)

There is trading between cGLD and cUSD, controlling the cUSD to peg to $1 value. 

There’s a variable fee on Celo Gold transactions that goes to bolstering the reserve. The rate is based on the reserve ratio. (lower the reserve ratio, the higher the transfer fee)

## 3 - Incentives

Incentive: Proof-of-bonded-stake model

encourages long-term holding of Celo Gold by weighting rewards according to the amount of Celo Gold bonded and length of time remaining in the bond.

## 4 - Governance

Anyone can propose protocol improvements along with an implementation fee.

Then voted on by Celo Gold holders weighted by their bonded-stake

> __Process of adding new stablecoins__
>
> Very similar to governance, just that instead of paying a submission fee proposers __have to stake Celo Gold__. 
> If the new stablecoin is __not backed by the shared reserve__, then no need voting. 

## Celo More details

__How to achive Stability__

![](/images/hybrid-crypto-collateralization/seigniorage-style-model.png)

The stability mechanism can be understood as a __hybrid crypto-collateralization and seigniorage-style model__. To maintain the stability of cUSD, the protocol sets incentives for users to adjust cUSD supply to match cUSD demand at the price peg. At a high level, the Celo expansion and contraction mechanism allows users to create new cUSD by sending 1 US Dollar worth of cGLD to the reserve, or to burn cUSD by redeeming them for 1 US Dollar worth of cGLD. This mechanism creates incentives such that when demand for cUSD rises users are incentivized to buy 1 US Dollar worth of cGLD on the market, exchange it with the protocol for one cUSD and then sell that cUSD for the market price (Expansion Cycle in below numerical example). This direct link between cUSD and cGLD is driving the market price of cUSD back towards 1 US Dollar without the need for the protocol to estimate the optimal expansion or contraction amounts. Having a crypto-only reserve allows for this process to be running constantly and transparently.

To bolster the reserve the expansion and contraction mechanism contains a spread, a small fee that is paid for every transaction within that mechanism. When the reserve ratio is below a certain threshold, a fraction of the block rewards (called epoch rewards) is distributed to the reserve. In times of a low reserve ratio, a variable transfer fee on cGLD transactions will also help to further bolster the reserve.

# Referece

https://medium.com/celoorg/a-look-at-the-celo-whitepaper-c0061118ffd4
https://medium.com/celoorg/diving-into-the-celo-price-stability-protocol-d7afd210609e
https://storage.googleapis.com/celo_whitepapers/Celo__A_Multi_Asset_Cryptographic_Protocol_for_Decentralized_Social_Payments.pdf
