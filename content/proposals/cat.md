+++
title = "OP_CAT"
description = "Overview of OP_CAT proposal to allow the concatenation of two values on the stack."
weight = 17
template = "docs/page.html"

[extra]
lead = ""
toc = true
+++


## Introduction

This BIP defines OP_CAT a new tapscript opcode which allows the concatenation of two values on the stack. This opcode would be activated via a soft fork by redefining the opcode OP_SUCCESS80.

When evaluated the OP_CAT instruction:
# Pops the top two values off the stack,
# concatenate the popped values together,
# and then pushes the concatenated value on the top of the stack.

OP_CAT fails if there are less than two values on the stack or if a concatenated value would have a combined size of greater than the maximum script element size of 520 Bytes.

OP_CAT follows the UNIX philosophy

## Specification

This proposal is being specified as a [draft BIP](https://github.com/EthanHeilman/op_cat_draft/blob/main/cat.mediawiki).

A draft implementation is included in the BIP in only 13 lines;

```
  if (stack.size() < 2)
    return set_error(serror, SCRIPT_ERR_INVALID_STACK_OPERATION);
  valtype vch1 = stacktop(-2);
  valtype vch2 = stacktop(-1);

  if (vch1.size() + vch2.size() > MAX_SCRIPT_ELEMENT_SIZE)
      return set_error(serror, SCRIPT_ERR_INVALID_STACK_OPERATION);

  valtype vch3;
  vch3.reserve(vch1.size() + vch2.size());
  vch3.insert(vch3.end(), vch1.begin(), vch1.end());
  vch3.insert(vch3.end(), vch2.begin(), vch2.end());

  popstack(stack);
  popstack(stack);
  stack.push_back(vch3);
```

## Use Cases

OP_CAT by adds a general purpose way to concatenate stack values would greatly increase the functionality of tapscript. 
This would enable the ability to construct and evaluate merkle trees and other hashed data structures in tapscript.

* Tree Signatures provide a multisignature script whose size can be logarithmic in the number of public keys and can encode spend conditions beyond n-of-m.
* Post-Quantum Lamport Signatures in Bitcoin transactions.
* Non-equivocation contracts made by enforcing rules on the spending transaction's nonce. These are useful building blocks for payment channels and other Bitcoin protocols.
* OP_CAT is sufficient to build vaults on bitcoin.
* The same behavior as OP_CHECKSIGFROMSTACK for both Shnorr and ECDSA signatures.
