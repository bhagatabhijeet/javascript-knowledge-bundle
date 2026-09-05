---
id: operators/arithmetic-operators
title: Arithmetic operators
type: operators
description: Perform numeric calculations with JavaScript's arithmetic operators, including exponentiation and remainder.
status: draft
tags:
  - javascript
  - fundamentals
  - operators
  - arithmetic
---

# Arithmetic operators

JavaScript's arithmetic operators work on numbers (and coerce operands toward numbers when possible).

```js
5 + 2   // 7
5 - 2   // 3
5 * 2   // 10
5 / 2   // 2.5
5 % 2   // 1, the remainder
5 ** 2  // 25, exponentiation
```

## Unary plus and minus

```js
+'42'   // 42, converts a string to a number
-'42'   // -42
```

## Increment and decrement

`++` and `--` have prefix and postfix forms that differ in what they return.

```js
let count = 1
count++    // returns 1, then count becomes 2 (postfix)
++count    // count becomes 3, then returns 3 (prefix)
```

## `+` is special

Unlike the other arithmetic operators, `+` also concatenates when either operand is a string. See [Dynamic typing and type coercion](../basics/dynamic-typing.md) for the coercion rules.

```js
1 + 1     // 2
'1' + 1   // '11'
```

## Related concepts

- [Assignment operators](./assignment-operators.md)
- [Operator precedence](./operator-precedence.md)
- [Dynamic typing and type coercion](../basics/dynamic-typing.md)

This draft was generated from general knowledge of MDN's JavaScript operator reference and has not been checked against a live source. It should receive human review before its status is promoted or a `verified` entry is added.
