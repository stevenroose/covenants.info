+++
title = "ANYPREVOUT"
description = "Overview of the Merklize All The Things proposal from Salvatore Ingala"
slug = "apo"
weight = 10
template = "docs/page.html"

[extra]
lead = "SIGHASH_ANYPREVOUT (APO)"
toc = true
+++


##### Links

- [Bitcoin Optech](https://bitcoinops.org/en/topics/sighash_anyprevout/)
- [anyprevout.xyz](https://anyprevout.xyz/)


## Introduction

`SIGHASH_ANYPREVOUT`, an updated version of `SIGHASH_NOINPUT`, is a proposal for a signature hash
(sighash) where the identifier for the UTXO being spent is not signed, allowing the signature to be
used with any UTXO that is protected by a similar script (i.e. uses the same public keys).

In other words, a transaction presigned with `SIGHASH_ANYPREVOUT` can be signed once and later
"attached" to multiple different outputs, as long as the conditions are met.

The original proposal for `SIGHASH_NOINPUT`, was mentioned in the [original Lightning Network
paper](https://lightning.network/lightning-network-paper.pdf) and a more detailed proposal in the
[Eltoo whitepaper](https://blockstream.com/eltoo.pdf).

## Specification

This proposal has been specified in
[BIP-118](https://github.com/bitcoin/bips/blob/master/bip-0118.mediawiki).


## Use Cases

APO was specifically proposed to bring about [Eltoo](/use-cases/eltoo), a more efficient Lightning
Channel update mechanism, but can be used to achieve various other use cases, such as
[Statechains](/use-cases/statechains) and [Spacechains](/use-cases/spacechains). It can also be used
to emulate a [CTV](/proposals/ctv)-like covenant and all its use-cases, but this emulation is both
more fragile (as you need to store signatures and pre-signed transactions) and less efficient, so it
is not an ideal solution to bring about these use-cases.
