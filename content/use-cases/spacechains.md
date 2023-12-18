+++
title = "Spacechains"
description = "Spacechains are tokenless blockchains that can be created with Bitcoin covenants"
weight = 35
template = "docs/page.html"

[extra]
lead = ""
toc = true
+++

##### Links

- [Explanatory Video][video]
- [Blind Merged Mining][bmm]

## Introduction

Spacechains are a model for creating blockchains that attach themselves to Bitcoin through a
[blind merged mining mechanism][bmm] that doesn't require Bitcoin miners or nodes to be aware
of the existence of these blockchains, they just see normal Bitcoin transactions that may (or
not) overpay in fees (due to the economics of spacechain mining) and include these in their
blocks.

Spacechains can be used to emulate all kinds of protocols that require a blockchain, like
protocols for transferring fungible and non-fungible tokens, open decentralized DNS
replacements, single-use seals and other ideas that involve ownership and require double-spend
protection.

Many of these ideas have been tested already in altcoins, but invariably these include a native
currency to be mined or staked in order for the blockchain to be operated, which inevitably
perverts the incentives and plague the usefulness of these ideas. Spacechains' main benefit
is that they don't require any native currency, although these can also be used [with safeguards
against pump-and-dump scams][p1wp].

## Technical Requirements

It is possible to build an [inefficient, fragile version of a Spacechain][supertestnet] without
covenants, but it only becomes a serious idea once it uses some kind of covenant that allows the
chain of BMM transactions to be immutable, which requires either [APO](/proposals/apo) or
[TXHASH](/proposals/txhash). [CTV](/proposals/ctv) could also work, although with a slight tradeoff
that makes it less appealing.

  [video]: https://www.youtube.com/watch?v=N2ow4Q34Jeg
  [bmm]: https://gist.github.com/RubenSomsen/5e4be6d18e5fa526b17d8b34906b16a5
  [p1wp]: https://medium.com/@RubenSomsen/21-million-bitcoins-to-rule-all-sidechains-the-perpetual-one-way-peg-96cb2f8ac302
  [supertestnet]: https://github.com/supertestnet/spacechain-launcher
