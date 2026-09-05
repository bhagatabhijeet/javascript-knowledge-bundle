---
id: operators/ternary-operator
title: Ternary operator
type: operators
description: "Write concise conditional expressions with JavaScript's only three-operand operator: condition ? a : b."
status: draft
tags:
  - javascript
  - fundamentals
  - operators
  - conditionals
---

# Ternary operator

The conditional (ternary) operator is JavaScript's only operator that takes three operands: a condition, followed by `?`, an expression to execute if truthy, followed by `:`, and an expression to execute if falsy.

```text
condition ? valueIfTrue : valueIfFalse
```

## Basic example

```js
// If customer points > 100, they are 'gold', otherwise 'silver'
let points = 110;
let type = points > 100 ? 'gold' : 'silver';

console.log(type); // 'gold'
```

## An expression, not a statement

Unlike `if`/`else` statements, the ternary operator evaluates directly to a value. This allows you to use it inline:

```js
let age = 20;
console.log(`You are ${age >= 18 ? 'an adult' : 'a minor'}.`);
```

## Avoid nesting

Nested ternaries save lines but severely reduce readability. Prefer `if`/`else`, a `switch` statement, or early returns when multiple branches are needed:

```js
// Difficult to read at a glance:
const label = score > 90 ? 'A' : score > 80 ? 'B' : score > 70 ? 'C' : 'F';
```

## Related concepts

- [JavaScript Operators](./javascript-operators.md)
- [Logical operators](./logical-operators.md)
- [Operator precedence](./operator-precedence.md)
- [Comparison operators](./comparison-operators.md)
- [Dynamic Types](../basics/dynamic-typing.md)
