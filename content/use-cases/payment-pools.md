+++
title = "Payment Pools"
description = "Overview of the payment pools / coinpools / joinpools use case for Bitcoin covenants."
date = 2021-05-01T08:20:00+00:00
updated = 2021-05-01T08:20:00+00:00
draft = false
weight = 24
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = "aka Coinpools, Joinpools"
toc = true
top = false
+++

##### Links

- [Bitcoin Optech](https://bitcoinops.org/en/topics/joinpools/)


## Introduction

Payment Pooks, Joinpools or Coinpools are constructions that allows multiple users to trustlessly
share ownership of one or more UTXOs. When funds are spent, it’s not possible to tell from the block
chain which pool member (or members) spent the funds. Joinpools can use presigned transactions or
proposed protocol features to ensure each member can unilaterally withdraw their funds from the pool
at any time.
