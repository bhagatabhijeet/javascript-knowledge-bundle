---
id: fundamentals/logical-operators
title: Logical operators
type: operators
description: Combine and short-circuit expressions with &&, ||, !, and the nullish coalescing operator ??.
status: draft
tags:
  - javascript
  - fundamentals
  - operators
  - logical
generated: { by: claude/sonnet-5, at: 2026-08-30T00:00:00Z }
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#binary_logical_operators
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Nullish_coalescing
---

# Logical operators

`&&`, `||`, and `!` work with truthy/falsy values, not just booleans, and `&&`/`||` return one of their operands rather than a strict `true`/`false`. See [Dynamic typing and type coercion](./dynamic-typing.md) for what counts as falsy.

```js
true && false   // false
true || false   // true
!true           // false
```

## Short-circuit evaluation

`&&` returns the first falsy operand or the last operand; `||` returns the first truthy operand or the last operand. The right side is only evaluated when needed.

```js
const user = { name: 'Ada' }
user && user.name        // 'Ada'
null && user.name         // null, user.name is never evaluated

const name = user.name || 'Guest'  // 'Ada'
```

This makes `&&` useful for conditional execution and `||` useful for fallback values — though `||` treats any falsy value (`0`, `''`, `false`) as "missing," which is often not what's intended.

## Nullish coalescing (`??`)

`??` falls back only when the left side is `null` or `undefined`, unlike `||`.

```js
const count = 0
count || 10   // 10, 0 is falsy
count ?? 10   // 0, 0 is neither null nor undefined
```

## Related concepts

- [The ternary operator](./ternary-operator.md)
- [Bitwise operators](./bitwise-operators.md)
- [Dynamic typing and type coercion](./dynamic-typing.md)

This draft was generated from general knowledge of MDN's JavaScript operator reference and has not been checked against a live source. It should receive human review before its status is promoted or a `verified` entry is added.
