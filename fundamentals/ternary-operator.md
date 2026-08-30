---
id: fundamentals/ternary-operator
title: The ternary operator
type: operators
description: "Write concise conditional expressions with JavaScript's only three-operand operator: condition ? a : b."
status: draft
tags:
  - javascript
  - fundamentals
  - operators
  - conditionals
generated: { by: claude/sonnet-5, at: 2026-08-30T00:00:00Z }
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Conditional_operator
---

# The ternary operator

The conditional (ternary) operator is JavaScript's only operator that takes three operands: a condition, a value if truthy, and a value if falsy.

```js
const age = 20
const status = age >= 18 ? 'adult' : 'minor'  // 'adult'
```

## An expression, not a statement

Unlike `if`/`else`, the ternary operator produces a value, so it can be used inline: in a template string, a function argument, or a JSX-like expression.

```js
console.log(`You are ${age >= 18 ? 'an adult' : 'a minor'}.`)
```

## Avoid nesting

Nested ternaries save lines but cost readability. Prefer `if`/`else`, an early return, or a lookup object once a decision has more than one branch.

```js
// Hard to scan at a glance:
const label = score > 90 ? 'A' : score > 80 ? 'B' : score > 70 ? 'C' : 'F'
```

## Related concepts

- [Logical operators](./logical-operators.md)
- [Operator precedence](./operator-precedence.md)
- [Dynamic typing and type coercion](./dynamic-typing.md)

This draft was generated from general knowledge of MDN's JavaScript operator reference and has not been checked against a live source. It should receive human review before its status is promoted or a `verified` entry is added.
