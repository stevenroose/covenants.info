+++
title = "The Great Script Restoration"
description = "Overview of the Great Script Restoration softfork proposal to re-enable old opcodes"
weight = 18
template = "docs/page.html"

[extra]
lead = ""
toc = true
+++


## Introduction

The _Great Script Restoration_ is an undertaking started by [Rusty
Russel](https://rusty.ozlabs.org/) and it aims to re-enable most of the Script opcodes that were
disabled early in bitcoin's history. In addition to re-enabling the lost opcodes, it also aims to
add a small set of new opcodes to further make Script an ergonomic and powerful scripting language
for expressing smart contracts.

A large part of the work is focussed on developing a cost function to safely express the cost of
each opcode used in a transaction's Script, so as to avoid denial-of-service (DoS) attack vectors.
The risk of DoS was a large motivation for the disabling of these opcodes at the time, so great care
has to be taken when they are re-enabled.

One of the opcodes that this project would re-enable is [`OP_CAT`](/extra/cat).

## Specification

Pending BIP and implementation.


## Implementation

Rusty is working on an implementation, but is also [seeking
help](https://iris.to/note1q00vc35lg59v65r4yfyzmr45vln0wdkrh2kdjsvnxrgdtgp7fd5syvdlqy) from anyone
interested to work with him on this project.
