+++
title = "TXHASH"
description = "Overview of OP_TXHASH and OP_CHECKTXHASHVERIFY."
weight = 23
template = "docs/page.html"

[extra]
lead = "OP_TXHASH and OP_CHECKTXHASHVERIFY"
toc = true
+++


##### Links

- [bitcoin-dev e-mail](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2022-January/019813.html)


## Introduction

This proposal originated on the bitcoin-dev mailing list where it was combined with
`OP_CHECKSIGFROMSTACK` to form an alternative to the combination of `OP_CHECKTEMPLATEVERIFY`
([CTV](/proposals/ctv)) and `SIGHASH_ANYPREVOUT` ([APO](/proposals/apo)). For more on the
combination of `OP_TXHASH` with `OP_CHECKSIGFROMSTACK`, check out the [CATT](/proposals/catt)
proposal.

The `OP_TXHASH` and `OP_CHECKTXHASHVERIFY` opcodes themselves can be considered an upgrade or
generalization of `OP_CHECKTEMPLATEVERIFY` and thus a way of enabling
advances [transaction templating](/use-cases/tx-templating).

Whereas CTV allows a user to commit to an entirely pre-specified spending transaction of a certain
transaction output, TXHASH allows the user to specify a range of individual bits of the spending
transaction to be included in the transaction template. The added flexibility solves a range of
difficulties that protocols face when using CTV (for example related to paying fees for the
pre-specified transactions), but it also enables additional independent use-cases like equality
checking of input and output values or scriptPubkeys.


## Specification

A BIP of the opcodes in this proposal is currently [in draft status on
GitHub](https://github.com/bitcoin/bips/pull/1500).

### Potential Extensions

The specification for this proposal defines a construction called a `TxFieldSelector` that can
directly be adopted to implement other constructions like
[`OP_TX`](/proposals/direct-introspection), an opcode for generalized introspection, or a new
Schnorr sighash flag.


## Use Cases

For use cases that are enabled this proposal, we refer to the more general use case page of
[transaction templating](/use-cases/tx-templating), or to the [summary
table](/overview/summary). For usage of `OP_TXHASH` together with some other opcodes, we refer
to the [CATT](/proposals/catt) proposal page.

