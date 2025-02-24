+++
title = "Ark"
description = "The Ark layer 2 protocol as a Bitcoin Covenant use case."
weight = 30
template = "docs/page.html"

[extra]
lead = ""
toc = true
+++

##### Links

- [bitcoin-dev e-mail](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2023-May/021694.html)
- [homepage](https://ark-protocol.org)
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


## Implementations

There are currently two teams working on an implementation of Ark. Both teams have opted to develop
a version of Ark that compromises some of the original design, which requires covenants, so that
their implementation can be deployed on bitcoin today without the need for protocol upgrades.
However, both teams also emphasize that the protocol and their implementation would greatly benefit
from having a covenant activate on bitcoin.

- [ark](https://github.com/ark-network/ark), a Golang implementation by [Ark
Labs](https://arklabs.to/) ([docs](http://arkdev.info/)).
- [bark](https://codeberg.org/ark-bitcoin/bark/), a Rust implementation by
[Second](https://second.tech/) ([docs](http://docs.second.tech/)).
