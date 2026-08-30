---
id: fundamentals/assignment-operators
title: Assignment operators
type: operators
description: Assign and update values with = and its compound arithmetic, logical, and nullish-coalescing forms.
status: draft
tags:
  - javascript
  - fundamentals
  - operators
  - assignment
generated: { by: claude/sonnet-5, at: 2026-08-30T00:00:00Z }
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators#assignment_operators
---

# Assignment operators

`=` assigns a value to a [variable](./variables.md). Compound assignment operators combine an operation with assignment.

```js
let total = 10
total += 5   // total = total + 5  -> 15
total -= 2   // total = total - 2  -> 13
total *= 2   // total = total * 2  -> 26
total /= 2   // total = total / 2  -> 13
total %= 5   // total = total % 5  -> 3
total **= 2  // total = total ** 2 -> 9
```

## Logical assignment

These short-circuit: the right side only evaluates, and the assignment only happens, when the condition holds.

```js
let a = null
a ??= 'default'   // assigns only if a is null or undefined -> 'default'

let b = 0
b ||= 5           // assigns only if b is falsy -> 5

let c = 1
c &&= 10          // assigns only if c is truthy -> 10
```

## Destructuring assignment

Arrays and objects can be unpacked into variables in a single assignment.

```js
const [first, second] = [1, 2]
const { name, role } = { name: 'Ada', role: 'Engineer' }
```

See [Objects and object literal patterns](./objects.md) and [Arrays](./arrays.md) for more on the structures being destructured.

## Related concepts

- [Arithmetic operators](./arithmetic-operators.md)
- [Logical operators](./logical-operators.md)
- [Variables and declarations](./variables.md)

This draft was generated from general knowledge of MDN's JavaScript operator reference and has not been checked against a live source. It should receive human review before its status is promoted or a `verified` entry is added.
