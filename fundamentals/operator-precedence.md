---
id: fundamentals/operator-precedence
title: Operator precedence
type: operators
description: Understand the order JavaScript evaluates operators in a compound expression, and when to use parentheses.
status: draft
tags:
  - javascript
  - fundamentals
  - operators
  - precedence
generated: { by: claude/sonnet-5, at: 2026-08-30T00:00:00Z }
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_precedence
---

# Operator precedence

When an expression mixes operators, precedence decides which one evaluates first — the same way multiplication binds tighter than addition in arithmetic.

```js
2 + 3 * 4    // 14, not 20: * binds tighter than +
(2 + 3) * 4  // 20, parentheses override precedence
```

## A partial ordering, highest to lowest

```text
()                      grouping
**                      exponentiation
* / %                   multiplicative
+ -                     additive
< <= > >=               relational
== != === !==           equality
&&                      logical AND
||  ??                  logical OR / nullish coalescing
? :                     ternary
= += -= ...             assignment
```

This is a simplified subset; the full table (including unary, bitwise, and comma operators) is in MDN's reference.

## Associativity

When operators share a precedence level, associativity decides evaluation order. Most operators are left-to-right; assignment and exponentiation are right-to-left.

```js
10 - 3 - 2   // 5, left-to-right: (10 - 3) - 2
2 ** 3 ** 2  // 512, right-to-left: 2 ** (3 ** 2)
```

## When precedence surprises

```js
const a = 1, b = 2
console.log(a + b === 3 ? 'yes' : 'no')  // 'yes': + binds before ===, which binds before ?:
```

Rather than memorizing the full table, use parentheses whenever an expression's evaluation order isn't immediately obvious to a reader.

## Related concepts

- [Arithmetic operators](./arithmetic-operators.md)
- [Logical operators](./logical-operators.md)
- [Bitwise operators](./bitwise-operators.md)

This draft was generated from general knowledge of MDN's JavaScript operator reference and has not been checked against a live source. It should receive human review before its status is promoted or a `verified` entry is added.
