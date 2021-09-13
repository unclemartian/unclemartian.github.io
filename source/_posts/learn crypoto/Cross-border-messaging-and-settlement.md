---
title: Cross-border settlement (SWIFT & CLS)
date: 2020-05-11 10:57:29
tags: crypto
---

# 几个系统的关联和区别

Clearing and settlement systems主要分为：

1. Net settlement systems
1. Real-time gross settlement (RTGS) systems

Cross-border messaging and settlement主要分为：

1. SWIFT (The Society for Worldwide Inter-bank Financial Telecommunications)
1. TARGET2
1. The European Banking Association (EBA)
1. Continuous linked settlement (CLS)
 
etc。
 
## TARGET2
 
Was originally introduced in 1999 to provide a real-time gross settlement system for the euro.
 
## The European Banking Association (EBA)
 
Was founded in 1985 to promote the European Currency Unit (ECU) 

## Continuous linked settlement (CLS)

A number of the world's largest __foreign exchange banks__ have joined together in 2002 to form a company: CLS Services Limited. 

They are __not allowed to compete for US domestic banking business__. CLS Bank is regulated by the Federal Reserve Bank, the US Central Bank, and can handle transactions denominated in 17 currencies: __GBP, USD, JPY, EUR__, CHF, CAD, AUD, DKK, NOK, SEK, __SGD, HKD__, NZD, __KRW__, ZAR, MXN and ILS.

has the ability to eliminate Herstatt risk (Payment vs Payment)

# CLS in details

CLS is a __Payment versus Payment (PvP) settlement__ system.

> Reduces the gross intraday liquidity required to settle individual FX transactions
> but introduce a time specific intraday liquidity position, the pay-in/pay-out time for each currency – which in many instances is outside ‘normal’ settlement times. 

## The consequences of Herstatt Risk

> This type of risk is named after Bank Herstatt that failed in 1974 and refers to risks that span more than one market – usually involving foreign exchange or securities instruments. 
> In the case of Bank Herstatt, the bank had entered into a number of foreign exchange deals and received payment from its European counterparts, but went into liquidation before it delivered the counter-value to its non European counterparts. 

> The only way to eliminate settlement exposure of this nature entirely is to settle both the debit and credit transaction at the same time using real-time gross settlement (RTGS) processes.

Today (2018) around 50% of cross-border FX transactions are processed via CLS

There has been historically a lack of transparency related to the status of payments. 

some national payment systems (e.g. Fedwire and CHIPS in US, the Australian, Swiss and Japanese RTGS systems) do not use SWIFT messages.

# Reference

https://wiki.treasurers.org/wiki/Payments_and_payment_systems
https://swiftinstitute.org/wp-content/uploads/2018/10/SIWP-2017-001-The-Future-of-Correspondent-Banking_FINALv2.pdf