+++
title = "OP_VAULT"
description = "Overview of OP_VAULT proposal to enable vaults in Bitcoin."
draft = false
weight = 17
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = ""
toc = true
top = false
+++


## Introduction

This proposal proposes two new tapscript opcodes that add consensus support for a specialized
covenant: `OP_VAULT` and `OP_VAULT_RECOVER`. These opcodes, in conjunction with
`OP_CHECKTEMPLATEVERIFY` ([CTV](/proposals/ctv)) allow users to enforce a delay period before
designated coins may be spent to an arbitrary destination, with the exception of a prespecified
"recovery" path. At any time prior to final withdrawal, the coins can be spent to the recovery path.

This proposal is explicitly aimed at enabling the [vaults](/use-cases/vaults) use case.


## Specification

This proposal is being specified as
[BIP-345](https://github.com/bitcoin/bips/pull/1421).

A [draft implementation](https://github.com/bitcoin-inquisition/bitcoin/pull/21) has been made for
Bitcoin Inquisition.


## Use Cases

For use cases that are enabled by CTV, we refer to the more general use case page of [transaction
templating](/use-cases/tx-templating), or to the [summary table](/overview/summary).

