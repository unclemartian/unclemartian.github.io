---
title: Auction models 一些拍卖模式介绍
date: 2021-03-01 23:22:28
tags:
---

# English Auction

英式拍卖是__最普通的一种拍卖方式__，其形式是：在拍卖过程中，拍卖标的物的竞价按照竞价阶梯由低至高、依次递增，当到达拍卖截止时间时，出价最高者成为竞买的赢家。

拍卖前，卖家可设定保留价，当最高竞价低于保留价时，卖家有权不出售此拍卖品。当然，卖家亦可设定无保留价，此时，到达拍卖截止时间时，最高竞价者成为买受人。

An English Auction, also referred to as __an open cry ascending auction__, starts by an auctioneer announcing the suggested opening bid or reserve price for the item on sale. 

> The buyers with interest in the item start placing bids on the item on sale, with the auctioneer accepting higher bids as they come.
>
> The buyer with the highest bid at any time is considered the one with a __standing bid__, which can only be displaced by a higher bid from the floor. 
>
> If there are no higher bids than the standing bid, the auctioneer announces the winner, and the item is sold to the person with the standing bid at a price equal to their bid. 
>
> If the reserve price is not met or no buyer places an economically fair bid, the seller can take the item off the market.

# Dutch auction

荷兰式拍卖亦称__“减价式拍卖”__。一种特殊的拍卖形式。

拍卖标的竞价由高到低依次递减直到第一个竞买人应价时击槌成交的拍卖。

减价式拍卖通常从非常高的价格开始，高得有时没有人竞价，这时，价格就以事先确定的降价阶梯，由高到低递减，直到有竞买人愿意接受为止。

如有两个或两个以上竞价人同时应价时，__转入增价拍卖形式__。

A Dutch auction is a price discovery process in which the auctioneer starts with the highest asking price and lowers it until it reaches a price level where the bids received will cover the entire offer quantity. 

> Alternatively, a Dutch auction is known as a __descending price auction or a uniform price auction__. 
>
> Dutch auctions are appropriate for instances where a large quantity of an item is being offered for sale, as opposed to just a single item.

## 特点

减价拍卖最大的优点在于：成交过程特别迅速，尤其是使用__表盘式无声拍卖方式，使拍卖过程机械化、电子化，交易速度大大加快__。

但是，叫价递减过程往往导致竞买人坐等观望，企盼价格不断减低，因而现场竞争气氛不够热烈。

# 其他一些种类

## 第一价格 Vs. 第二价格

### First-Price Auction

if your bid wins, you pay exactly what you bid. This maximizes revenue potential for the seller.

### Second-Price Auction

if your bid wins, you pay $0.01 above the second highest bid in the auction. In this type of auction, it is in your best interest to bid the highest amount you are willing to pay, knowing that often you will end up paying less than that amount.

Game theory suggests that __a buyer might allocate a higher max bid price to a purchase item__ if there is a chance to settle a transaction with a final price that is significantly lower than his bid. 

As a result, the transactions may – on average – __settle with higher prices__ which makes second-price auction as a transaction model for ad trading attractive for suppliers.

## Sealed-bid Auction

与English auction相对的，是Sealed-bid Auction。

在封闭式拍卖的情况下，竞价者只能知道自己的出价，而不知其他竞价者的出价。相反，开放式拍卖中竞价者彼此知道自己的出价。

> 封闭式拍卖通常用于企业竞拍，开放式拍卖通常用于个人竞拍。

### 1st-price

Sealed first-price auction or blind auction, also known as a __first-price sealed-bid auction (FPSB)__. This type of auction is distinct from the English auction, in that bidders can only submit one bid each. Furthermore, as bidders cannot see the bids of other participants

From the theoretical perspective, this kind of bid process has been argued to be __strategically equivalent to the Dutch auction__.

### 2nd-price

__Vickrey auction, also known as a sealed-bid second-price auction__. This is identical to the sealed first-price auction __except that__ the winning bidder pays the second-highest bid rather than his or her own.

## Variation

### Auction by the candle

A type of auction, used in England for selling ships, in which the highest bid laid on the table by the time a burning candle goes out wins.

### Scottish auction 

All bidding should be completed within a certain time interval, which provides bidders an appropriate amount of time for considerations and avoids precipitate actions.

### Japanese auction

the current price changes continuously according __to the auctioneer's clock__, rather than by bidders' outcries. 

Bidders can only decide if and when to exit the arena. 

> At first glance, this seems equivalent to English auction: apparently, in an English auction, it is a dominant strategy for each buyer whose price is above the displayed price, to always bid the minimal allowed increment (e.g. one cent) above the displayed price, so the price should increase continuously. 
>
> However, in real-life English auctions, jump bidding is often observed: buyers increase the displayed price much more than the minimal allowed increment. 
>
> Obviously, jump-bidding is not possible in a Japanese auction.

1. The winning buyer is the buyer with the highest valuation;
1. The final price is the second-highest valuation.

# References

https://en.wikipedia.org/wiki/Auction
https://goodwaygroup.com/blog/first-price-vs-second-price-auction

https://en.wikipedia.org/wiki/First-price_sealed-bid_auction
