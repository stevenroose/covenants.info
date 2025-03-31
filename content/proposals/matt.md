+++
title = "CCV & MATT"
description = "Overview of the MATT proposal from Salvatore Ingala"
weight = 40
template = "docs/page.html"

[extra]
lead = "Merkleize All The Things"
toc = true
+++


##### Links
- [OP_CHECKCONTRACTVERIFY BIP draft](https://github.com/bitcoin/bips/pull/1793)
- [OP_CHECKCONTRACTVERIFY bitcoin-core implementation](https://github.com/bitcoin/bitcoin/pull/32080)
- [MATT homepage](https://merkle.fun)

## Introduction

`OP_CHECKCONTRACTVERIFY` (`OP_CCV`) is a proposed opcode that enables a new primitive called _state-carrying UTXOs_. This primitiv allows a UTXO to contain a commitment to data that can be introspected and computed upon in Script, with the resulting embedded in the output UTXOs (if desired).

Together with an opcode that allows the creation of _vector commitments_ (like `OP_CAT` or [`OP_PAIRCOMMIT`](https://github.com/bitcoin/bips/pull/1699); other options are possible), `OP_CCV` enables _fraud proofs_ for arbitrary computations, widely extending the class of smart contracts that are possible in Script.

## Specification

The specifications of `OP_CHECKCONTRACTVERIFY` are available in the [CCV BIP draft](https://github.com/bitcoin/bips/pull/1793) and the [bitcoin-core implementation](https://github.com/bitcoin/bitcoin/pull/32080).

These specifications are only for the `OP_CCV` opcode, and therefore should be paired with an opcode for vector commitments for a complete proposal for MATT [as originally proposed](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2022-November/021182.html).

## Use Cases

`OP_CHECKCONTRACTVERIFY` is designed to enable a generic programming construct; therefore, the list of applications is very open-ended, and it plays well in conjunction with other opcodes.

Therefore, the following applications are some known applications that have been discussed or demonstrated, but the list is not exhaustive.

Note: in what follows, `OP_CAT` can always be replaced with any opcode that enables vector commitments.

### Vaults

`CCV` on its own enables minimal functional vaults (demonstrated as part as the bitcoin-core implementation). Such vaults would be very fitting for usage in [recovery spending paths](https://delvingbitcoin.org/t/using-op-vault-for-recovery/150) for a wallet like [Liana](https://github.com/wizardsardine/liana).

`OP_CCV` + `OP_CTV` enables fully featured vaults that are essentially equivalent to `OP_VAULT` + `OP_VAULT_RECOVER` + `OP_CTV`.

`OP_CCV` + `OP_AMOUNT` also enables fully-featured vaults, although less efficient when unvaulting to multiple destinations.

#### Recovery/inheritance

An application of vault-like spending conditions is as an alternative to timelocks for spending paths used for recovery or inheritance use cases, as in wallets like [Liana](https://github.com/wizardsardine/liana).

This has been discussed, for example, [here](https://delvingbitcoin.org/t/using-op-vault-for-recovery/150).

`OP_CCV` alone suffices for those use-cases.

### Fraud proofs for arbitrary computation

`OP_CCV + OP_CAT` enables fraud proofs for arbitrary computations.

This enables _optimistic smart contracts_, where some state transition enforced by the covenant are not validated in Script, but simply _asserted_ to be true; in case the party making the assertion is lying, other parties can challenge the assertion, and an arbitration protocol ultimately adjudicates the winner - under the assumption that the challenger's transaction are not being censored.

- Python implementation in the pymatt framework for the [fraud proof protocol](https://github.com/Merkleize/pymatt/blob/master/matt/hub/fraud.py)
- [Optimization and cost estimates](https://delvingbitcoin.org/t/games-in-the-head-and-fraud-proofs-for-the-plebs/446)
- [Verification of arbitrary function compiled to Risc-V in Bitcoin Script](https://github.com/halseth/elftrace)

### Optimistic sidechains/rollups

A widely discussed type of optimistic smart contracts is an optimistic sidechain or rollup, or a client-side-validation protocol like [Shielded CSV](https://eprint.iacr.org/2025/068).

General fraud proofs improve over designs based on systems like BitVM by removing the 1-of-N assumption, and vastly reducing the worst-case on-chain footprint in case of challenges.

### Any-order exits in shared UTXOs

Together with an opcode like `OP_AMOUNT` for introspection of the output amounts, `OP_CCV` would allow protocols for unilateral, any-order exit from shared UTXOs.

Johan Halseth [wrote to the bitcoin-dev mailing
list](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2023-May/021719.html) how MATT,
together with `OP_CAT` can be used to implement [Payment Pools](/use-cases/payment-pools).

### Other applications

- [DLCs](/use-cases/dlcs) - `OP_CCV` can be used for Transferable DLCs and several other applications.
- [Aggregate delegated exits for shared UTXOs](https://delvingbitcoin.org/t/aggregate-delegated-exit-for-l2-pools/297) - in combinations with `OP_CAT`, and `OP_AMOUNT` (or other opcodes for amount introspection): allows multiple parties to join forces in unilaterally exiting a shared UTXO, at a fraction of the cost they would have if they exit individually. 
