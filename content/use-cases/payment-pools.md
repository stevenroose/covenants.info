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

Like being written [by Jeremy Rubin](https://rubin.io/bitcoin/2021/12/10/advent-13/),

> Mechanistically, all that is required of a Payment Pool is that:
>
> - It’s a single (shared) UTXO
> - Every user can get their funds out unilaterally
> - A set of users can authorize spend the funds
> - Unspent funds/change stays in the pool

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



#### CoinPool design:

CoinPools are an implementation of the "robust payment pools" idea, as described in the [bitcoin-dev
mailing list post by Antoine
Riard](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2020-June/017964.html):

> A Split_Tx enables a unilateral exit from the CoinPool, in case it's not
> possible to use a cooperative Pool_Tx path. This transaction spends the
> UTXO via the Merkle branch into two outputs:
> - a _withdraw_ output paying to the pool participant who initiated a
> transaction
> - a _recursive_ output paying to the new instance of a CoinPool, which
> contains all the same participants except the one who just withdrew

