+++
title = "Introduction"
description = "Introduction to Bitcoin covenant proposals and use cases"
weight = 10
template = "docs/page.html"

[extra]
lead = ""
toc = false
+++


This collaborative web page attempts to be a comprehensive overview of different Bitcoin
[**covenant**](https://bitcoinops.org/en/topics/covenants/) use cases and consensus change proposals.

Use the side-bar to explore the different use cases and proposals or check out the
[summary table](/overview/summary).


### What are "covenants"

The term _covenant_ is borrowed from legal speak and is not very well known in common language.
When we talk about "covenants" in bitcoin terms, what we actually mean is **the ability for bitcoin
Script to introspect the transaction it is executed in**. So another, more descriptive, term to use
instead of covenants would be "**transaction introspection**" or "introspection opcodes"
specifically when we're talking about Script opcodes.

Bitcoin Script, the scripting language that we use to express conditions for spending _unspent
transaction outputs (UTXOs)_, has a set of opcodes that enables users to restrict spending of
outputs based mostly on signatures and timing constraints (so-called time-locks).

In principle, Script already has certain introspective capabilities:
- `OP_CHECKSIG`, which checks a signature over the "sighash" of a transaction, which hashes
  together a bunch of properties of the transaction. It only checks the signature though, and
  doesn't allow for actually looking into the fields that make up the sighash.
- `OP_CHECKLOCKTIMEVERIFY`, which checks that the `nLockTime` field of the transaction is higher
  than a certain value
- `OP_CHECKSEQUENCEVERIFY`, which equivalently checks that the `nSequence` field of an input is
  higher than a certain value.

However, even though the above three opcodes exist today and in principle provide some very
rudimentary introspection in the spending transaction, their capabilities is extremely restricted
and intended for some very specific usage.

So, when we speak about "covenants" or "transaction introspection", what we mean is _**the
generalized capability of Script to look into or assert various properties of the spending
transaction**_.

### Contributing

This web page is definitely not a finished work. Since it is collaborative, everyone is very much
invited to contribute to it [on GitHub](https://github.com/stevenroose/covenants.info)!

Apart from content contributors, some help would also be appreciated on the website; we use the
static site generator [Zola](https://getzola.org/) and the [AdiDoks](https://adidoks.org/) theme.
