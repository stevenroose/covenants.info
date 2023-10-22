+++
title = "CATT"
description = "Overview of CATT Bitcoin covenant proposal: Covenant All The Things."
date = 2021-05-01T08:20:00+00:00
updated = 2021-05-01T08:20:00+00:00
draft = false
weight = 30
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = "Covenant All The Things"
toc = true
top = false
+++


## Introduction

CATT is a proposal to collectively enable a set of independently specified opcodes that together
enable a very wide range of use cases. The idea is to provide very raw and simple buildig blocks
that can be used by developers to build use cases instead of focussing on use case-specific opcodes.


The different parts of CATT are the following:

- `OP_TXHASH` (and `OP_CHECKTXHASHVERIFY`), as [described here](/docs/proposals/txhash)
- `OP_CAT`, an opcode to concatenate stack items that formerly existed on Bitcoin but hash been
  [disabled](https://github.com/bitcoin/bitcoin/commit/4bd188c4383d6e614e18f79dc337fbabe8464c82#diff-27496895958ca30c47bbb873299a2ad7a7ea1003a9faa96b317250e3b7aa1fefR94)
  - or alternatively an opcode to calculate the SHA-256 hash of concatenated data, called `OP_SHA256CAT` [by Salvatore](https://github.com/ariard/bitcoin-contracting-primitives-wg/issues/25#issuecomment-1377942333) or `OP_MULTISHA256` [by Rusty](https://twitter.com/rusty_twit/status/1715607011776409858)
- `OP_CHECKSIGFROMSTACK`, an [opcode](https://bitcoinops.org/en/topics/op_checksigfromstack/) to
  check signatures for arbitrary messages, that is currently active on [Elements](https://github.com/ElementsProject/elements/)
- an opcode to tweak a public key with a scalar, like either
  - `OP_TWEAKVERIFY` like active [in
    Elements](https://github.com/ElementsProject/elements/blob/master/doc/tapscript_opcodes.md)
  - `OP_TWEAK`, a non-VERIFY version of the above
    (alternatively named `OP_KEYADDTWEAK` [by
    Rusty](https://twitter.com/rusty_twit/status/1715607009230545341))


An _extended_ version of CATT can additionally include the following:

- `OP_TX`, enabling generalized direct introspection
- 64-bit arithmethic opcodes


## Specification

The individual pieces of this transaction are specified in different BIPs:

- `OP_TXHASH`: [proposed BIP](https://github.com/bitcoin/bips/pull/1500)
- `OP_CAT`: [proposed BIP](https://github.com/EthanHeilman/op_cat_draft/blob/main/cat.mediawiki)
- `OP_CHECKSIGFROMSTACK`: no BIP yet, but already
  [implemented](https://github.com/ElementsProject/elements/blob/f08447909101bfbbcaf89e382f55c87b2086198a/src/script/interpreter.cpp#L1399)
  and active in Elements


## Use Cases

For use cases that are enabled this proposal, we refer to the more general use case page of
[transaction templating](/docs/use-cases/tx-templating), or to the [summary
table](/docs/overview/summary). For usage of `OP_TXHASH` together with some other opcodes, we refer
to the [CATT](/docs/proposals/catt) proposal page.


