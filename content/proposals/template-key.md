+++
title = "Template Key"
description = "Overview of the Template Key proposal by Brandon Black"
slug = "template-key"
#weight = 10
template = "docs/page.html"

[extra]
lead = "Template Key"
toc = true
+++

## Introduction

Template Key is an alternative to `SIGHASH_ANYPREVOUT` that defines the same
two new tapscript key types (33-byte and 1-byte keys beginning with `1`). The
new signature hashing modes defined by Template Key are more flexible than
traditional signature hashes, but attempt to be easy to reason about and
implement. In addition to defining these new hashing modes for tapscript keys,
they are specified as behavior for `OP_CHECKTEMPLATEVERIFY` with 33-byte
arguments.

## Specification

This proposal has been specified in
[BIP Template Key](https://github.com/reardencode/bips/blob/bip-template-key/bip-template-key.mediawiki).


## Use Cases

Template Key aims to enable everything that APO does, and to satisfy a useful
array of other hashed template use-cases which might have been unduly
constrained by CTV (or pre-signed APO output covenants). For Ark, it offers
hashing modes which include all-but-first input/output.

