+++
title = "MATT"
description = "Overview of the MATT proposal from Salvatore Ingala"
weight = 40
template = "docs/page.html"

[extra]
lead = "Merkleize All The Things"
toc = true
+++


##### Links

- [homepage](https://merkle.fun)


## Introduction

MATT is a proposal to enable a fraud-proof system for smart contracts on
Bitcoin. It can compile very general programs into a merkleized execution tree, for which fraud
proofs can be executed on the Bitcoin main chain.


## Specification

A WIP specification of the new opcodes MATT would introduce can be found [on
GitHub](https://github.com/ariard/bitcoin-contracting-primitives-wg/issues/25)

Currently, they are the following:

- `OP_CHECKINPUTCOVENANTVERIFY`
- `OP_CHECKOUTPUTCOVENANTVERIFY`
- `OP_CAT`
- `OP_PUSH_ANNEX_RECORD`


## Use Cases

A very wide range of use cases can be enabled by MATT, though it's ability to execute fraud proofs
for arbitrary programs. When it comes to covenants, however, it seems that transaction introspection
is achieved primarily by using the individual opcodes enabled by the proposal.

### Vaults

Salvatore has written an [in-depth
example](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2023-April/021588.html) of how
vaults could be implemented using MATT, as well as a [draft
implementation](https://github.com/bitcoin-inquisition/bitcoin/compare/24.0...bigspider:bitcoin-inquisition:matt-vault)
for Bitcoin Inquisition.

### Joinpools

Johan Halseth [wrote to the bitcoin-dev mailing
list](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2023-May/021719.html) how MATT,
together with `OP_CAT` can be used to implement [Payment Pools](/use-cases/payment-pools).

### CTV

Johan Halseth wrote how [CTV](/proposals/ctv) can be [implemented using
MATT](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2023-June/021730.html).

