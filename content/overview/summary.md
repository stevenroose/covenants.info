+++
title = "Summary Table"
description = "Summary table of Bitcoin covenant proposals and use cases"
weight = 20
template = "docs/page.html"

[extra]
lead = ""
toc = false
+++



## Use Cases

use case           | apo   | ctv   | txhash | tluv | intro | vault | matt
-------------------|-------|-------|--------|------|-------|-------|-----
Lightning Symmetry | yes   | csfs* | csfs*  | ?    | yes   | no    | yes
Vaults             | no    | yes   | tap*   | yes  | tap*  | yes   | yes
Payment Pools      | no    | no    | tap*   | yes  | tap*  | no    | yes
Ark                | half  | half  | yes    | no   | yes   | ~ctv  | yes
Fraud Proofs       | no    | no    | no     | no   | no    | no    | yes
Statechains        | yes   | csfs* | csfs*  | ?    | yes   | no    | yes
Spacechains        | yes   | yes   | yes    | ?    | ?     | ~ctv  | ?
Congestion Control | no    | yes   | yes    | no   | yes   | ~ctv  | yes


Glossary:

- tap*: yes if combined with something that allows turning a script into a Taproot, plus often
  also `OP_CAT`
- csfs*: yes if combined with `OP_CHECKSIGFROMSTACK`
- ~ctv: yes but only because the `OP_VAULT` proposal also includes `OP_CTV`


## Development Status

proposal             | status
-|-
ANYPREVOUT           | [BIP][bip118] and active on Inquisition
CTV                  | [BIP][bip119] and active on Inquisition
OP_VAULT             | [BIP 345][bip345] — Withdrawn (May 2025), superseded by [BIP 443][bip443] (CCV)
TLUV                 | idea
TXHASH               | [BIP 346][bip-txhash] and [Bitcoin Core Implementation][pr-txhash]
Direct Introspection | ideas (but [active on Liquid][intro-liquid])
MATT                 | [BIP 443][bip443] and [Bitcoin Core Implementation][pr-matt]
Template Key         | [early draft BIP][bip-template-key]


## Developer Support

The bitcoin wiki has a page where certain prominent bitcoin developers have indicated their support
for various proposals, some of them adding a rationale behind their support:
- [https://en.bitcoin.it/wiki/Covenants_support](https://en.bitcoin.it/wiki/Covenants_support)


[bip118]: https://github.com/bitcoin/bips/blob/master/bip-0118.mediawiki
[bip119]: https://github.com/bitcoin/bips/blob/master/bip-0119.mediawiki
[bip345]: https://github.com/bitcoin/bips/blob/master/bip-0345.mediawiki
[bip443]: https://github.com/bitcoin/bips/blob/master/bip-0443.mediawiki
[bip-txhash]: https://github.com/bitcoin/bips/blob/master/bip-0346.mediawiki
[bip-template-key]: https://github.com/reardencode/bips/blob/bip-template-key/bip-template-key.mediawiki

[pr-txhash]: https://github.com/bitcoin/bitcoin/pull/29050
[pr-matt]: https://github.com/bitcoin/bitcoin/pull/32080

[intro-liquid]: https://github.com/ElementsProject/elements/blob/master/doc/tapscript_opcodes.md
