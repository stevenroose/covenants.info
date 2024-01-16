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

`OP_CAT` is a simple opcode that concatenates two byte strings together in Bitcoin Script.

Andrew Poelstra once wrote a two-part series of blog posts to showcase how the `OP_CAT` opcode can
in itself effectively enable covenants:

- [CAT and Schnorr tricks 1](https://www.wpsoftware.net/andrew/blog/cat-and-schnorr-tricks-i.html)
- [CAT and Schnorr tricks 2](https://www.wpsoftware.net/andrew/blog/cat-and-schnorr-tricks-ii.html)

It's important to clarify that this proposal doesn't aim to introduce covenants to Bitcoin. Instead,
it is focused on introducing an opcode that holds broad utility across various scenarios. The
potency of several covenant proposals increases substantially when they can be integrated with the
functionality provided by `CAT`.


## Specification

A BIP of the `OP_CAT` opcode is currently [in draft status on
GitHub](https://github.com/bitcoin/bips/pull/1525).

An implementation on Bitcoin Inquisition [is also
available](https://github.com/bitcoin-inquisition/bitcoin/pull/39).

