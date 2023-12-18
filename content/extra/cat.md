+++
title = "OP_CAT"
description = "Overview of OP_CAT proposal to allow the concatenation of two values on the stack."
weight = 17
template = "docs/page.html"

[extra]
lead = ""
toc = true
+++


## Introduction

`OP_CAT` is a simple opcode concatenates two byte strings together in Bitcoin Script.

Andrew Poelstra once wrote a two-part series of blog posts to showcase how the `OP_CAT` opcode can
in itself effectively enable covenants:

- https://www.wpsoftware.net/andrew/blog/cat-and-schnorr-tricks-i.html
- https://www.wpsoftware.net/andrew/blog/cat-and-schnorr-tricks-ii.html

Obviously, however, a proposal to enable `OP_CAT` is not a proposal to add covenants to Bitcoin, but
simply a proposal to add an opcode that is very useful generally for many use cases. In fact,
several of the covenant proposals become significantly more powerful when they can be combined with
`OP_CAT`.



## Specification

A BIP of the `OP_CAT` opcodes is currently [in draft status on
GitHub](https://github.com/bitcoin/bips/pull/1525).

An implementation on Bitcoin Inquisition [is also
available](https://github.com/bitcoin-inquisition/bitcoin/pull/39).

