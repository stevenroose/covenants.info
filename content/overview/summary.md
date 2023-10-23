+++
title = "Summary Table"
description = "Summary table of Bitcoin covenant proposals and use cases"
weight = 20
sort_by = "weight"
template = "docs/page.html"

[extra]
lead = ""
toc = false
top = false
+++



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
