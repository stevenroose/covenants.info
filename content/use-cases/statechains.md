+++
title = "Statechains"
description = "Statechains: non-custodial scalable UTXO transfer based on Eltoo"
weight = 34
template = "docs/page.html"

[extra]
lead = ""
toc = true
+++

##### Links

- [Article](https://medium.com/@RubenSomsen/statechains-non-custodial-off-chain-bitcoin-transfer-1ae4845a4a39)
- [Blind Statechains conference presentation](https://www.youtube.com/watch?v=09HcYRjDkMA)
- [Video presentations](https://www.youtube.com/watch?v=CKx6eULIC3A)

## Introduction

A statechain is a sequence of holders that succeed each other in owning the same UTXO while it sits
in the blockchain untouched. It basically works by making that UTXO be redeemable by two keys: one
controlled by the current owner and the other by a Statechain Entity (SE), i.e. a semi-trusted server.
Transfers happen by the current owner sending their key to the next and notifying the SE that a
transfer took place. The thing that is being transferred is called a _statecoin_.

Unless the SE colludes with one of the previous owners of the _statecoin_, it cannot steal the UTXO.

[Mercury Layer][mercury] is an improvement upon the idea that makes it even more
appealing: by switching the key shares controlled by the SE and the current/next owner on every
transfer, it becomes possible for the SE to delete previous key shares and thus it is impossible for
it to retroactively become malicious and steal funds, therefore the system can be operated
non-custodially.

Since the UTXO never moves onchain this system offers high scalability promises. It can also be used
to transfer Ordinals NFTs, Lightning channels while they are opened, DLC bets and everything that
exists at the UTXO level.

## Technical Requirements

Covenants are needed to operate this system at maximum scalability and reliability, for the current
owner of a _statecoin_ to be able to redeem his UTXO without cooperation from the SE, it must receive,
at the time of the transfer, a presigned _"backup" withdraw transaction_ that spents the locked UTXO
to a Bitcoin address under his control.

To prevent previous owners from using their old _backup transactions_ to steal the UTXO, a mechanism
like the one used in [Eltoo](/proposals/eltoo) is employed, such that if an previous owner tries to
steal the current owner can always overwrite his efforts and claim the funds.

[Mercury Layer][mercury] implements a degraded variant of Statechains that works today, creating
_backup transactions_ that start with a huge `nLockTime` and decrease these with each transfer. This
has two drawbacks that don't exist in the full system with covenants:

  a. Backup withdrawals may take a long time, which is bad when an immediate withdraw is needed;
  b. Some users are forced to fall to the chain and pay unnecessary fees at seemingly random times,
which may make them value _statecoins_ that are about to expire less than _statecoins_ that will
expire long in the future.

  [mercury]: https://mercurylayer.com/
