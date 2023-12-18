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

use case           | apo   | ctv   | txhash | tluv | intro | vault | catt | matt | tplk
-|-|-|-|-|-|-|-|-|-
Lightning Symmetry | yes   | csfs* | csfs*  | ?    | yes   | no    | yes  | yes  | yes
Vaults             | no    | yes   | tap*   | yes  | tap*  | yes   | yes  | yes  | tap*
Payment Pools      | no    | no    | tap*   | yes  | tap*  | ~ctv  | yes  | yes  | tap*
Ark                | half  | half  | yes    | no   | yes   | ~ctv  | yes  | yes  | yes
Fraud Proofs       | no    | no    | no     | no   | no    | no    | no   | yes  | no
Statechains        | yes   | no    | yes    | ?    | yes   | no    | yes  | yes  | yes
Spacechains        | yes   | half  | yes    | ?    | no    | ~ctv  | yes  | no   | yes
Congestion Control | no    | yes   | yes    | no   | yes   | ~ctv  | yes  | yes  | yes


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
OP_VAULT             | [draft BIP][bip345] and Inquisition [patch][pr-vault]
TLUV                 | idea
TXHASH               | [draft BIP][bip-txhash] and [Bitcoin Core Implementation][pr-txhash]
Direct Introspection | ideas (but [active on Liquid][intro-liquid])
CATT                 | partial BIP'ed, partial ideas
MATT                 | very detailed ideas
Template Key         | [early draft BIP][bip-template-key]



[bip118]: https://github.com/bitcoin/bips/blob/master/bip-0118.mediawiki
[bip119]: https://github.com/bitcoin/bips/blob/master/bip-0119.mediawiki
[bip345]: https://github.com/bitcoin/bips/pull/1421
[bip-txhash]: https://github.com/bitcoin/bips/pull/1500
[bip-template-key]: https://github.com/reardencode/bips/blob/bip-template-key/bip-template-key.mediawiki

[pr-txhash]: https://github.com/bitcoin/bitcoin/pull/29050
[pr-vault]: https://github.com/bitcoin-inquisition/bitcoin/pull/21

[intro-liquid]: https://github.com/ElementsProject/elements/blob/master/doc/tapscript_opcodes.md
