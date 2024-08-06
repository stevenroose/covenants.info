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
- [dlc-dev mailing list post](https://lists.linuxfoundation.org/pipermail/bitcoin-dev/2022-February/019864.html)
- [dlcs implemented with different covenant proposals](https://github.com/bennyhodl/dlcat)

## Introduction

Discreet Log Contracts (DLCs) are a type of smart contract that allows two parties to create a bet or financial contract based on the future outcome of an event, as determined by an oracle. While DLCs are already possible on Bitcoin without covenants, the introduction of certain covenant proposals could significantly improve their usability.

## Covenant-Enhanced DLCs

With the introduction of covenant proposals like [CTV](/proposals/ctv) or [CAT](/extra/CAT), DLCs can be optimized to:
1. Dramatically reduce computational costs
2. Decrease the amount of data exchanged between parties
3. Simplify the implementation of oracle thresholds
4. Potentially eliminate the need for attestation point multiplication

These improvements address several user experience concerns and engineering difficulties associated with the current DLC protocol, making it much faster and more efficient to enter into a DLC.

## Key Benefits
- **Performance Improvement**: Up to 30x improvement in worst-case scenarios compared to using MuSig2 adaptor signatures.
- **Reduced Computation**: Eliminates the need for multiple EC multiplications per Contract Execution Transaction (CET).
- **Simplified Oracle Thresholds**: Easier implementation of multi-oracle setups without increasing computational complexity.
- **Reduced Communication Complexity**: The amount of data exchanged between parties becomes constant, regardless of the number of outcomes.
- **Near-Instant Setup**: These improvements allow DLCs to be set up almost instantly, even on resource-constrained devices and poor internet connections.

## Trade-offs

- Slightly larger witness size in non-cooperative cases
- Transactions become distinguishable from other protocols (no longer scriptless)

Despite these minor drawbacks, covenant-enhanced DLCs offer substantial improvements in the efficiency of entering a DLC, making them more practical for widespread adoption and use on various devices.
