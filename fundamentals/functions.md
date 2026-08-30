---
id: fundamentals/functions
title: Function declarations and expressions
type: js-basics
description: Learn the primary ways to define functions and how hoisting and closures change behavior.
status: stable
verified: { by: human:bhagatabhijeet, at: 2026-08-29T00:00:00Z }
tags:
  - javascript
  - fundamentals
  - functions
---

# Function declarations and expressions

Functions are reusable units of behavior. JavaScript supports both declarations and expressions, and each form interacts with hoisting and execution context differently.

## Function declaration

```js
function greet(name) {
  return `Hello, ${name}`
}
```

## Function expression

```js
const greet = function (name) {
  return `Hello, ${name}`
}
```

## Arrow functions

Arrow functions capture the surrounding `this` value and are useful for concise callbacks.

```js
const double = (value) => value * 2
```

## Why this matters

Understanding function shape helps you choose the right model for callbacks, iteration, and encapsulated logic.

## Related concepts

- [Variables and declarations](./variables.md)
- [Objects and object literal patterns](./objects.md)
- [Async JavaScript](./async.md)
- [Types of functions](./function-types.md)
