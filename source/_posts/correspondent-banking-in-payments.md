---
title: Correspondent Banking in Payments
date: 2020-04-15 21:48:36
tags:
---

# Opening Message

The SWIFT message is merely the instruction: the movement of funds is done by debiting and crediting several accounts at each institution and relies on banks maintaining accounts with each other (either directly or through intermediary banks). Check [this link](https://gendal.me/2013/11/24/a-simple-explanation-of-how-money-moves-around-the-banking-system/) out. 

# Swift

1973 The Society for Worldwide Interbank Financial Telecommunication ("S.W.I.F.T."). Or SWIFT

Not for profit organisation

Provide hardware with global data centres, typically:
1. banks connect via HSM
1. corporates connect via a service bureau (who is host and manage a HSM).

Typically the payload is message (FIN service) of file based (FileAct)

> FIN service: 基于SWIFT网络最主要的应用。即日常银行发送、接收、制作的业务报文都基于FIN服务。比如MT103、MT700等等报文。

It can work in a number of modes (Realtime/Store and Forward) and in the case of Fin will perform basic validations on submittal.

> SWIFT FileAct: 提供交互和存储与转发两种文件自动传输方式，适合大批量数据的传输。

## ISO20022

ISO20022 又称为UNIFI (UNIversal Financial Industry)

是2004年由国际标准化组织制定并发布的国际标准，提供了一种面向业务建立通用报文的解决方案。

ISO20022是一个以XML为基础之讯息标准，主要系由SWIFT组织XML讯息标准(SWIFT XML,MX)、贸易产业标准FIX组织标准(FIXml)及金融衍生性商品交易讯息标准(FpML)，为主要骨干所形成之架构。

## MT103, MT202

MT103, MT202 are message types in SWIFT communication.

MT103是银行客户的汇款格式，有汇款人，收款人名称和账户等信息，收款人可以凭以贷记收款人账户；
MT202是银行间头寸汇划报文格式，没有受益人名称和账号信息，收款行自然无法入账。

swift MT103报文名称叫做 single customer credit transfer 也就是单笔客户的汇款
swift MT202报文名称叫做 general fin inst transfer 也就是金融机构间资金调拨报文

MT 103 type corresponds to single credit customer transfer, in which a payment is settled directly to the account. Whereas, MT 202 is a cover transfer in which a correspondent bank’s NOSTRO account is involved through which remittance is further transferred to beneficiary.

Generally wire transfers use a Swift MT103 to transfer money on behalf of their client. There are exeptions to this. Such as SEPA transfers in europe, internal book transfer, and in some countries they do not use use Swift for their own currency (like russia). Also note that sometimes payments get netted so the amount on the MT103 may be different.

Banks use MT202 (and MT200) to transfer money on their own behalf and cash management purposes.

So there are many MT103 send throughout the day for clients, and only a few MT202/MT200 are send for funding/defunding banks own nostro accounts.

# Correspondent Banking

Most domestic (ach) systems are file based, especially for low value clearing. Urgent or high value domestic payments will be message based.

Globally, there is a progression to near real-time domestic payments. New systems are based on ISO20022 (file) , or Swift(message).


# Reference

https://www.quora.com/Do-all-wire-transactions-have-MT103-and-MT202-Or-does-MT202-take-place-only-for-non-direct-relationships-between-originator-and-beneficiary-bank-transfers
https://www.quora.com/What-is-the-SWIFT-messaging-protocol
