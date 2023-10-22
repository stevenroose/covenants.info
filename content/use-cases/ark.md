+++
title = "Ark"
description = "The Ark layer 2 protocol as a Bitcoin Covenant use case."
date = 2021-05-01T08:20:00+00:00
updated = 2021-05-01T08:20:00+00:00
draft = false
weight = 30
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = ""
toc = true
top = false
+++

##### Links

- [bitcoin-dev e-mail](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2023-May/021694.html)
- [homepage](https://www.arkpill.me/)
- [presentation](https://roose.io/presentations/understanding-ark.pdf)


## Introduction

Ark is a newly proposed layer two protocol that aims to enable the ability to make cheap off-chain
transactions while not suffering from the same adoption difficulties as the Lightning Network:
inbound liquidity and channel management. It relies on a central service provider to condense an
unlimited number of transactions of so-called virtual UTXOs (VTXOs) that happen off-chain into a
single on-chain transaction. Because Ark is inter-operable with the Lightning Network, Ark users can
also send and receive Lightning payments.

Ark is currently still in design phase and no specification or implementation exists to date.


## Technical Requirements

In theory it is possible to build Ark on Bitcoin without covenants, but with the use of [transaction
templating](/use-cases/tx-templating), the protocol becomes a lot less interactive.

Herefore, ideally Ark would be built on some transaction templating mechanism. It would be possible
to use [CTV](/proposals/ctv), but ideally something more flexible like
[TXHASH](/proposals/txhash) would be preferred.

