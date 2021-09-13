---
title: 'MataMask状态：Dropped & Replaced'
date: 2021-05-01 18:18:21
tags: crypto
---

__Dropped & Replaced__ is a tx status in MetaMask.

有两种状态：

1. Dropped Transaction
2. Dropped & Replaced Transaction

# Dropped Transaction

## 定义

由broadcasted状态 --> 变为dropped状态

是Ethereum nodes（也就是矿工）的操作。

A Dropped transaction can be re-broadcasted and re-appear as a Pending transaction (by any Eth node).

## Dropped 常见原因

- Ethereum nodes dropped it from transaction pool
  - Ethereum nodes 指的是 Geth or Parity
  - most likely due to lower gas price

- Max amount of Pending transactions an Ethereum node reached(this
  - depends on settings/limits of the individual clients

# Dropped & Replaced Transaction

## 成立条件

1. a newly created transaction with the same FROM account nonce is accepted and confirmed
2. previous txhash invalidated

## Dropped & Replaced 原因

- The earlier tx had low gas price which would take a very long time to confirm,
  - a second tx with higher gas price was created to replace it

- The Ethereum Node that the wallet/service connected to was not fully synced, and an incorrect nonce was used

- User-initiated to replace or cancel a pending transaction

# Reference

https://info.etherscan.com/transaction-dropped-replaced/
