+++
title = "DLCs"
description = "Discreet Log Contracts (DLCs) as a Bitcoin Covenant use case."
weight = 30
template = "docs/page.html"

[extra]
lead = ""
toc = true
+++

##### Links

- [dlc specifications](https://github.com/discreetlogcontracts/dlcspecs/)
- [dlc-dev mailing list post](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2022-January/019808.html)
- [dlcs implemented with different covenant proposals](https://github.com/bennyhodl/dlcat)

## Introduction

Discreet Log Contracts (DLCs) are a type of smart contract that allows two parties to create a bet or financial contract based on the future outcome of an event, as determined by an oracle. While DLCs are already possible on Bitcoin without covenants, the introduction of certain covenant proposals could significantly improve their usability.

## Covenant-Enhanced DLCs

With the introduction of covenant proposals like [CTV](/proposals/ctv), [CAT](/extra/CAT) and [TXHASH](/proposals/txhash), DLCs can be optimized to:

1. Dramatically reduce computational costs
2. Decrease the amount of data exchanged between parties
3. Simplify the implementation of oracle thresholds
4. Potentially eliminate the need for attestation point multiplication

These improvements address several user experience concerns and engineering difficulties associated with the current DLC protocol, making it much faster and more efficient to enter into a DLC.

Note: [CAT](/extra/CAT) does not reduce the computation costs as much as other proposals, since you to grind the tx data to get the [last byte correct for CAT covenants](https://github.com/taproot-wizards/purrfect_vault/?tab=readme-ov-file#limitations-and-considerations) (EC operations much slower than a hash).

### Transferable DLCs

Covenant proposals like [TXHASH](/proposals/txhash) or [CCV](/proposals/matt) enable DLC transferability by allowing restrictions on specific inputs and outputs. This means that DLC positions can be sold or transferred to other parties without requiring interaction with the original counterparty, significantly improving the liquidity and utility of DLCs.

#### Recursive Covenants

Covenant proposals that enable recursive covenants, such as [CAT](/extra/CAT) and [CCV](/proposals/matt) (when combined with [PAIRCOMMIT](https://github.com/bitcoin/bips/blob/018d28c967b3f2b747ecb4e5a85d0b5f9f4ec79a/bip-PC.md)), allow for even more sophisticated DLC operations in addition to simplification and cost reduction of transferability:

- **Position Splitting**: Participants can divide their DLC position into smaller pieces, each backed by a proportional amount of the original collateral
- **Collateral Management**: Enables committing to rules for adding or adjusting collateral within the DLC structure

## Key Benefits

- **Performance Improvement**: Up to 30x improvement in worst-case scenarios compared to using MuSig2 adaptor signatures.
- **Reduced Computation**: Eliminates the need for multiple EC multiplications per Contract Execution Transaction (CET).
- **Simplified Oracle Thresholds**: Easier implementation of multi-oracle setups without increasing computational complexity.
- **Reduced Communication Complexity**: The amount of data exchanged between parties becomes constant, regardless of the number of outcomes.
- **Near-Instant Setup**: These improvements allow DLCs to be set up almost instantly, even on resource-constrained devices and poor internet connections.
- **Transferability**: DLC positions can be sold or transferred to other parties without requiring interaction with the original counterparty, significantly improving the liquidity and utility of DLCs. ([CAT](/extra/CAT) / [TXHASH](/proposals/txhash) / [CCV](/proposals/matt))
- **Position Splitting**: Participants can divide their DLC position into smaller pieces, each backed by a proportional amount of the original collateral. ([CAT](/extra/CAT) / [CCV](/proposals/matt) + [PAIRCOMMIT](https://github.com/bitcoin/bips/blob/018d28c967b3f2b747ecb4e5a85d0b5f9f4ec79a/bip-PC.md))
- **Collateral Management**: Enables committing to rules for adding or adjusting collateral. ([CAT](/extra/CAT) / [CCV](/proposals/matt) + [PAIRCOMMIT](https://github.com/bitcoin/bips/blob/018d28c967b3f2b747ecb4e5a85d0b5f9f4ec79a/bip-PC.md))

## Trade-offs

- Slightly larger witness size in non-cooperative cases
- Transactions become distinguishable from other protocols (no longer scriptless)

Despite these minor drawbacks, covenant-enhanced DLCs offer substantial improvements in the efficiency of entering a DLC, making them more practical for widespread adoption and use on various devices.
