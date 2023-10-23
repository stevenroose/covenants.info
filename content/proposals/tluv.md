+++
title = "TLUV"
description = "Overview of OP_TAPLEAF_UPDATE_VERIFY (TLUV) Bitcoin covenant proposal"
weight = 22
template = "docs/page.html"

[extra]
lead = "OP_TAPLEAF_UPDATE_VERIFY"
toc = true
+++


##### Links

- bitcoin-dev e-mails: [overview](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2021-September/019419.html), [technical details](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2021-September/019420.html)
- [Bitcoin Optech](https://bitcoinops.org/en/newsletters/2021/09/15/#covenant-opcode-proposal)



## Introduction

A new `OP_TAPLEAF_UPDATE_VERIFY` (TLUV) opcode is proposed that takes information about the taproot
input being spent, makes modifications described in a tapscript, and requires that the result be
equivalent to the scriptPubKey in the output in the same position as the input. This allows TLUV to
constrain where the bitcoins can be spent (the definition of a covenant), similar to other proposed
opcodes such as OP_CHECKSIGFROMSTACK (CSFS) and OP_CHECKTEMPLATEVERIFY ([CTV](/proposals/ctv)).

Where it differs from previous proposals is that it allows the created of the tapscript to specify
modifications to both the internal key and a tapscript tree (MAST).

Ideally TLUV would be activated in conjuction with some additional opcode or mechanism to introspect
the amounts of inputs and outputs in the current transaction.

