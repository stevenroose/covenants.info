+++
title = "MATT"
description = "Overview of the MATT proposal from Salvatore Ingala"
date = 2021-05-01T08:20:00+00:00
updated = 2021-05-01T08:20:00+00:00
draft = false
weight = 40
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = "Merkleize All The Things"
toc = true
top = false
+++


##### Links

- [homepage](https://merkle.fun)

## Introduction

MATT is a proposal to enable a fraud-proof system for smart contracts on
Bitcoin. It can compile very general programs into a merklized execution tree, for which fraud
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
