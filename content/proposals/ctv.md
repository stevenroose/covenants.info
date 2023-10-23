+++
title = "CTV"
description = "Overview of OP_CHECKTEMPLATEVERIFY"
weight = 15
template = "docs/page.html"

[extra]
lead = "OP_CHECKTEMPLATEVERIFY"
toc = true
+++


##### Links

- [homepage](https://utxos.org/)
- [Bitcoin Optech](https://bitcoinops.org/en/topics/op_checktemplateverify/)


## Introduction

`OP_CHECKTEMPLATEVERIFY` (CTV) is a proposed new opcode that takes a commitment hash as a parameter
and requires any transaction executing the opcode include a set of outputs that match the
commitment. This makes it possible to create an address that specifies how any funds received to
that address may be spent—a design known in Bitcoin as a covenant.

Originally introduced under the name `OP_CHECKOUTPUTSHASHVERIFY` (COSHV) and later renamed
`OP_SECURETHEBAG`, the proposal initially focused on the ability to create congestion control
transactions where a spender pays a single address using CTV which, when confirmed to a suitable
depth, then assures several receivers that they can each be paid. This two-step process can probably
be used anywhere payment batching is an option but it can likely reduce fees even further than
payment batching.

Later versions of the proposal placed greater emphasis on other contracts and covenants that could
be created using the new opcode, such as the ability to create channel factories, vaults, and
coinjoin transactions in new ways that might simplify construction or reduce fees. Other authors
have mentioned that the new opcode could possibly be used to allow users to trustlessly pool their
funds together into a single UTXO in a way that would increase privacy.

Criticisms of the proposal have focused on it being too specific to the congestion control use case
rather than providing a generic covenant capability.


## Specification

This proposal has been specified in
[BIP-119](https://github.com/bitcoin/bips/blob/master/bip-0119.mediawiki).


## Use Cases

For use cases that are enabled by CTV, we refer to the more general use case page of [transaction
templating](/use-cases/tx-templating), or to the [summary table](/overview/summary).
