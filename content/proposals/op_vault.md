+++
title = "OP_VAULT"
description = "Overview of OP_VAULT proposal to enable vaults in Bitcoin."
weight = 17
template = "docs/page.html"

[extra]
lead = ""
toc = true
+++


> **Note:** BIP 345 (OP\_VAULT) was withdrawn on May 8, 2025, superseded by BIP 443
> (OP\_CHECKCONTRACTVERIFY). See the [CCV/MATT proposal](/proposals/matt/) for the current
> approach to vaults.

## Introduction

This proposal proposes two new tapscript opcodes that add consensus support for a specialized
covenant: `OP_VAULT` and `OP_VAULT_RECOVER`. These opcodes, in conjunction with
`OP_CHECKTEMPLATEVERIFY` ([CTV](/proposals/ctv)), allow users to enforce a delay period before
designated coins may be spent to an arbitrary destination, with the exception of a pre-specified
"recovery" path. At any time prior to final withdrawal, the coins can be spent to the recovery path.

This proposal is explicitly aimed at enabling the [vaults](/use-cases/vaults) use case.


## Specification

This proposal was specified as
[BIP 345](https://github.com/bitcoin/bips/blob/master/bip-0345.mediawiki).

A [draft implementation](https://github.com/bitcoin-inquisition/bitcoin/pull/21) has been made for
Bitcoin Inquisition.


## Use Cases

For use cases that are enabled by CTV, we refer to the more general use case page of [transaction
templating](/use-cases/tx-templating), or to the [summary table](/overview/summary).

