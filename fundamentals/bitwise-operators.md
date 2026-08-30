---
id: fundamentals/bitwise-operators
title: Bitwise operators
type: operators
description: Manipulate integers at the bit level with JavaScript's bitwise AND, OR, XOR, NOT, and shift operators.
status: draft
tags:
  - javascript
  - fundamentals
  - operators
  - bitwise
generated: { by: claude/sonnet-5, at: 2026-08-30T00:00:00Z }
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#bitwise_operators
---

# Bitwise operators

Bitwise operators convert operands to 32-bit integers and operate on their individual bits.

```js
5 & 3    // 1,  AND   (0101 & 0011 = 0001)
5 | 3    // 7,  OR    (0101 | 0011 = 0111)
5 ^ 3    // 6,  XOR   (0101 ^ 0011 = 0110)
~5       // -6, NOT (inverts all bits)
```

## Shifts

```js
5 << 1    // 10, shift left (multiply by 2)
5 >> 1    // 2,  shift right, sign-preserving
-5 >>> 1  // large positive number, shift right, zero-filling
```

## When these come up

Bitwise operators are uncommon in everyday application code. They show up in bit-flag configurations, hashing, low-level binary protocols, and performance-sensitive numeric tricks (for example `n | 0` as a fast integer truncation). For readability, prefer explicit boolean logic or `Math` methods unless the bit-level behavior is the point.

## Related concepts

- [Logical operators](./logical-operators.md)
- [Operator precedence](./operator-precedence.md)

This draft was generated from general knowledge of MDN's JavaScript operator reference and has not been checked against a live source. It should receive human review before its status is promoted or a `verified` entry is added.
