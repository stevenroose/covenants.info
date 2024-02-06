+++
title = "Payment Pools"
description = "Overview of the payment pool use case for Bitcoin covenants."
weight = 24
template = "docs/page.html"

[extra]
lead = "aka Coinpools, Joinpools"
toc = true
+++

##### Links

- [Bitcoin Optech](https://bitcoinops.org/en/topics/joinpools/)


## Introduction

Payment Pools, Joinpools or Coinpools are constructions that allows multiple users to trustlessly
share ownership of one or more UTXOs. When funds are spent, it’s not possible to tell from the block
chain which pool member (or members) spent the funds.

### Joinpools

Some form of payment pools, Joinpools, are possible today as they use pre-signed transactions to
ensure that each participant in the pool gets their money back. However, they suffer from the
problem that any participant not cooperating requires breaking up the pool into pieces.

Using [CTV](/proposals/ctv) a slight improvement on this idea is possible, reducing some of the
need for interactivity and reducing the number of pieces a pool is broken up into from `N` to
`log(N)` where `N` is the number of participants.


## Robust Payment Pools

In the context of covenants, designs have been made for payment pools that don't suffer this
"break-up problem" when a participant disappears. In these designs, every user that is not
cooperating can be pushed out of the pool without breaking up the pool further than needed. This
means that the remaining active users can continue operations after the non-cooperative participant
has been exited.

Designs like this are proposed using the more expressive proposals like [TLUV](/proposals/tluv),
[MATT](/proposals/matt) and [CATT](/proposals/catt).

