+++
title = "Direct Introspection"
description = "Overview of direct introspection opcodes as Bitcoin covenants proposal."
weight = 28
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = "OP_TX or individual opcodes"
toc = true
top = false
+++


##### Links

- [bitcoin-dev e-mail on OP_TX](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2022-May/020450.html)
- [specification of introspection opcodes in Elements](https://github.com/ElementsProject/elements/blob/master/doc/tapscript_opcodes.md#new-opcodes-for-additional-functionality)

## Introduction

A very straight-forward way to achieve covenans is to give the Script of a transaction's inputs
direct access into the entire transaction's data. If the script can inspect any part of the
transaction, it is by definition introspective and can enforce any possible constraint on the
transaction's properties.

Technically, there are two ways direct transaction introspection can be realized, either through
various different opcodes to _query_ various different aspects of the transaction, to be put onto
the stack by the script execution engine; or by introducing a single opcode together with an
additional specifier of what parts of the transaction you actually want.


#### Individual opcodes

An example of the former was [introduced into
Elements](https://github.com/ElementsProject/elements/blob/master/doc/tapscript_opcodes.md) in the
shape of the following opcodes (excluding the ones only relevant for Elements):

- `OP_INSPECTINPUTOUTPOINT`
- `OP_INSPECTINPUTVALUE`
- `OP_INSPECTINPUTSCRIPTPUBKEY`
- `OP_INSPECTINPUTSEQUENCE`
- `OP_PUSHCURRENTINPUTINDEX`
- `OP_INSPECTOUTPUTVALUE`
- `OP_INSPECTOUTPUTSCRIPTPUBKEY`
- `OP_INSPECTVERSION`
- `OP_INSPECTLOCKTIME`
- `OP_INSPECTNUMINPUTS`
- `OP_INSPECTNUMOUTPUTS`
- `OP_TXWEIGHT`

Implementation and usage of these opcodes is rather straight-forward.


#### General opcode

An example of the latter approach would be `OP_TX`, a single opcode that takes a specifier from the
stack that the user can use to indicate what parts of the transaction they want. The benefits of
this approach are that more transaction data be requested using less script bytes.

A potential implementation of `OP_TX` could be based on the specification of `OP_TXHASH` as
described in [this section](/proposals/txhash/#potential-extensions) where the same specifier can be
used but instead of the individual elements being hashed together for `OP_TXHASH`, they can be
pushed onto the stack with `OP_TX`.



