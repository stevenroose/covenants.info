+++
title = "APO"
description = "Overview of the Merklize All The Things proposal from Salvatore Ingala"
date = 2021-05-01T08:20:00+00:00
updated = 2021-05-01T08:20:00+00:00
draft = false
weight = 20
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = "SIGHASH_ANYPREVOUT"
toc = true
top = false
+++


##### Links

- [Bitcoin Optech](https://bitcoinops.org/en/topics/sighash_anyprevout/)


## Introduction

`SIGHASH_ANYPREVOUT`, an updated version of `SIGHASH_NOINPUT`, is a proposal for a signature hash
(sighash) where the identifier for the UTXO being spent is not signed, allowing the signature to be
used with any UTXO that’s protected by a similar script (i.e. uses the same public keys).

The original proposal for `SIGHASH_NOINPUT`, was included in the [Eltoo](/docs/use-cases/eltoo)
paper.


## Specification

This proposal has been specified in
[BIP-118](https://github.com/bitcoin/bips/blob/master/bip-0118.mediawiki).


## Use Cases

APO was specifically proposed to bring about Eltoo, but can be used to achieve various other use
cases. However,

