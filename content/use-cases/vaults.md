+++
title = "Vaults"
description = "Bitcoin cold-storage vaults as a Bitcoin Covenant use case."
weight = 21
template = "docs/page.html"

[extra]
lead = ""
toc = true
+++


##### Links

- [Bitcoin Optech](https://bitcoinops.org/en/topics/vaults/)

## Introduction

Vault are a type of covenant that require two separate transactions to appear in two different
blocks in order for a user to spend money from their wallet. The first transaction signals that
someone is attempting to spend the money and gives the user a chance to block the second transaction
that completes the spend.

A vault protocol specifies a minimum amount of time or number of blocks that must pass between the
two transactions, giving the user that amount of time to notice if someone stole their private key
and is attempting to steal their money. If the user detects the theft attempt, most vault designs
also allow the user to either send the money to a safe address that uses a more secure script or to
permanently destroy the money to prevent the thief from profiting from their attack.

Some vault designs rely on covenants that require consensus changes to Bitcoin. Other vault designs
use existing protocol features plus techniques such as signing transactions long in advance of
needing them and then destroying the means to sign alternative transactions (either by securely
deleting the signing key or by using multisig to ensure multiple independent keys would need to be
compromised).


## Requirements

Vaults generally need two things:
- a way to enforce certain properties on the input and output values of a transaction
- a way to enforce a delay period after which a certain script can be activated.

These two requirements are surprisingly non-trivial to enforce and hence vaults have been an
extensive topic of discussion within the covenants debate.


## OP_VAULT

Vaults are such a popular use case that [a set of opcodes are proposed](/proposals/op_vault)
explicitly to enable vaults.

