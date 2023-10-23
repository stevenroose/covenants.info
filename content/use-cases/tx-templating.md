+++
title = "Transaction Templating"
description = "Generalized use case of Bitcoin transaction templating"
weight = 10
template = "docs/page.html"

[extra]
lead = ""
toc = true
+++


## Introduction

Transaction Templating is more of a generalization of various use cases than a concrete use case. We
want to refer here to the use of covenants to construct a series of either entirely or partially
pre-specified transactions that is committed to in an output.

Similar constructions to this are currently possible by pre-signing the transactions. The drawback
of this is that large signature and public keys have to be put onto the transactions and that the
entire transaction has to be specified upfront. Proposals for better transaction templating
constructions will mostly focus on being less costly and more flexible with regards to how complete
the specification of the transactions has to be.

Generally, transaction templating is useful to reduce interactivity in various multi-user and/or
off-chain protocols.


## Proposals

The following proposals focus on enabling transaction templating:

- [CTV](/proposals/ctv)
- [TXHASH](/proposals/txhash)

Other proposals can be used to achieve some form of improved transaction templating, but are not
primarily proposed to enable it.


