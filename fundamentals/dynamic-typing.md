---
id: fundamentals/dynamic-typing
title: Dynamic typing and type coercion
type: js-basics
description: How JavaScript's dynamic type system assigns types at runtime and coerces values across operations.
status: draft
tags:
  - javascript
  - fundamentals
  - types
  - coercion
generated: { by: claude/sonnet-5, at: 2026-08-29T00:00:00Z }
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Data_structures
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Equality_comparisons_and_sameness
---

# Dynamic typing and type coercion

JavaScript is dynamically typed: a variable's type is not declared up front. It is determined by whatever value is currently assigned, and it can change after reassignment.

```js
let value = 42        // number
value = 'now a string' // string, same variable
value = true            // boolean
```

Use `typeof` to inspect a value's current type at runtime:

```js
typeof value // depends on what value currently holds
```

## Type coercion

JavaScript automatically converts values between types in many operations. This is often useful but can produce surprising results.

```js
'5' + 1        // '51' (number coerced to string)
'5' - 1        // 4   (string coerced to number)
1 + true       // 2   (true coerced to 1)
[] + []        // ''  (both arrays coerced to strings, then concatenated)
[] + {}        // '[object Object]'
```

`+` prefers string concatenation when either operand is a string; other arithmetic operators (`-`, `*`, `/`) coerce operands toward numbers.

## Equality: `==` vs `===`

`==` (loose equality) coerces operands before comparing; `===` (strict equality) does not.

```js
'5' == 5   // true, '5' is coerced to a number
'5' === 5  // false, different types

null == undefined  // true
null === undefined // false
```

Prefer `===` by default. Reach for `==` only when the coercion is intentional and well understood.

## Falsy and truthy values

In a boolean context, values coerce to `true` or `false`. The falsy values are:

```text
false, 0, -0, 0n, '', null, undefined, NaN
```

Everything else, including `'0'`, `[]`, and `{}`, is truthy.

## Related concepts

- [Primitive data types](./primitive-types.md)
- [Variables and declarations](./variables.md)
- [Objects and object literal patterns](./objects.md)
- [Comparison operators](./comparison-operators.md)
- [Equality operators](./equality-operators.md)
- [Logical operators](./logical-operators.md)

This draft was generated from general knowledge of MDN's JavaScript documentation and has not been checked against a live source. It should receive human review before its status is promoted or a `verified` entry is added.
