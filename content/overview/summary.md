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

use case           | apo   | ctv  | txhash | tluv | intro | vault | catt | matt
-|-|-|-|-|-|-|-|-
Lightning Symmerty | yes   | no   | yes    | ?    | yes   | no    | yes  | yes
Vaults             | no    | no   | tap*   | yes  | tap*  | yes   | yes  | yes
Payment Pools      | no    | no   | tap*   | yes  | tap*  | ~ctv  | yes  | yes
Ark                | half  | half | yes    | no   | yes   | ~ctv  | yes  | yes
Fraud Proofs       | no    | no   | no     | no   | no    | no    | no   | yes
Congestion Control | no    | yes  | yes    | no   | yes   | ~ctv  | yes  | yes


Glossary:

- tap*: yes if combined with something that allows turning a script into a Taproot, plus often
  also `OP_CAT`
- ~ctv: yes but only because the `OP_VAULT` proposal also includes `OP_CTV`



## Development Status

proposal             | status
-|-
ANYPREVOUT           | [BIP][bip118] and Inquisition deployment
CTV                  | [BIP][bip119] and Inquitision deployment
OP_VAULT             | [draft BIP][bip345] and Inquisition [patch][pr-vault]
TLUV                 | idea
TXHASH               | [draft BIP][bip-txhash]
Direct Introspection | indeas
CATT                 | partial BIP'ed, partial ideas
MATT                 | very detailed ideas



[bip118]: https://github.com/bitcoin/bips/blob/master/bip-0118.mediawiki
[bip119]: https://github.com/bitcoin/bips/blob/master/bip-0119.mediawiki
[bip345]: https://github.com/bitcoin/bips/pull/1421
[bip-txhash]: https://github.com/bitcoin/bips/pull/1500

[pr-vault]: https://github.com/bitcoin-inquisition/bitcoin/pull/21
