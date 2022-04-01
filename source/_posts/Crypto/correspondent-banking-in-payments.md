---
title: 【Crypto】 Correspondent Banking in Swift Payments
date: 2020-04-15 21:48:36
tags: crypto
---

# Opening Message

The SWIFT message is merely the instruction: the movement of funds is done by debiting and crediting several accounts at each institution and relies on banks maintaining accounts with each other (either directly or through intermediary banks). Check [this link](https://gendal.me/2013/11/24/a-simple-explanation-of-how-money-moves-around-the-banking-system/) out.

## Definition 

### Correspondent Bank

“an arrangement under which one bank (correspondent) holds deposits owned by other banks (respondents) and provides payment and other services to those respondent banks” (BIS, 2016).

### Settlement

“the discharge of an obligation in accordance with the terms of the underlying contract” (BIS, Glossary),

## The Risks

1. Market, 
1. FX, 
1. credit
1. counterparty 
1. regulatory risk (e.g. Anti-Money Laundering (AML) and Counter Terrorism Financing (CTF))

What is __settlement risk__? The bank could default. (eg. Herstatt Bank)

## Result

Continued decrease in correspondent banking relationships, regulatory compliance is certainly playing a role

50% of banks have <= 2 correspond banks

# SWIFT Org

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

1. swift MT103报文名称叫做 single customer credit transfer 也就是单笔客户的汇款
1. swift MT202报文名称叫做 general fin inst transfer 也就是金融机构间资金调拨报文

MT 103 type corresponds to single credit customer transfer, in which a payment is settled directly to the account. Whereas, MT 202 is a cover transfer in which a correspondent bank’s NOSTRO account is involved through which remittance is further transferred to beneficiary.

Generally wire transfers use a Swift MT103 to transfer money on behalf of their client. There are exeptions to this. Such as SEPA transfers in europe, internal book transfer, and in some countries they do not use use Swift for their own currency (like russia). Also note that sometimes payments get netted so the amount on the MT103 may be different.

Banks use MT202 (and MT200) to transfer money on their own behalf and cash management purposes.

So there are many MT103 send throughout the day for clients, and only a few MT202/MT200 are send for funding/defunding banks own nostro accounts.

# Correspondent Banking

No bank have relationship with every possible bank that customers may want to transfer money to. So, they usually keep relationships with a correspondence bank; one (or multiple) banks for each transfer currency.

Bank would transfer money from your account into a holding account; and send a notice to their correspondence bank (usually over SWIFT). 

Most domestic (ach) systems are file based, especially for low value clearing. Urgent or high value domestic payments will be message based.

Globally, there is a progression to near real-time domestic payments. New systems are based on ISO20022 (file) , or Swift(message).

## DNS and RTGS

### deferred net settlement (DNS)

also called Designated-time net settlement system (DNS).

A net settlement mechanism which settles on a net basis at the end of a predefined settlement cycle.

### Real-time gross settlement (RTGS)

Specialist funds transfer systems where the transfer of money takes place from one bank to any another on a "real-time" and on a "gross" basis.


## Nostro and Vostro accounts

Also called __Correspondent bank account__. Nostro and Vostro are variations on the Latin words "ours" and "yours," respectively.

These accounts are established to enable the domestic bank to make payments or money transfers on behalf of the foreign bank.

Nostro accounts with debit balances are __considered cash assets__. Contrarily, Vostro accounts with a credit balance are __considered liabilities__

> Both the Central Bank of China and Central Bank of France, credit the IOUs to the Bank. The Banks (namely Bank of China and BNP Paribas) now have an IOU Credit liability for further credit into the account of the beneficiary which would be Xing Framers and John Pierre Imports respectively.

![](/images/lemonade-money-transfer.jpg)

## Pre-Fund Model

> The pre-fund model is the most common and works on per corridor basis.
> This model makes it possible for sending agents to settle the net amount with the beneficiary bank quickly.
> Periodically, sending agent will replenish their prefunded account with the beneficiary banks using SWIFT. In some places, net off is not allowed.

# Reference

## SWIFT Protocol

https://www.quora.com/Do-all-wire-transactions-have-MT103-and-MT202-Or-does-MT202-take-place-only-for-non-direct-relationships-between-originator-and-beneficiary-bank-transfers
https://www.quora.com/What-is-the-SWIFT-messaging-protocol

## Correspondent Bank

https://www.quora.com/How-are-international-SWIFT-wire-transfers-settled
https://www.quora.com/How-does-money-transfer-between-banks-and-different-countries-work
https://www.investopedia.com/ask/answers/051815/what-difference-between-nostro-and-vostro-account.asp

## Swift Institution

https://swiftinstitute.org/wp-content/uploads/2018/10/SIWP-2017-001-The-Future-of-Correspondent-Banking_FINALv2.pdf
