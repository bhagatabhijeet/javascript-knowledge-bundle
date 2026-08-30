---
id: javascript/fundamentals/variables
title: Variables and declarations
type: Concept
description: Understand when to use let, const, and var for safe and predictable behavior.
status: stable
trust: human-reviewed
stale: false
tags:
  - javascript
  - fundamentals
  - variables
---

# Variables and declarations

JavaScript variables are the entry point for state and data flow. The choice between `let`, `const`, and `var` affects scope, reassignment, and hoisting behavior.

## `const`

Use `const` for values that should not be reassigned. It gives strong intent and keeps code easier to reason about.

```js
const answer = 42
// answer = 43 // Throws in strict mode
```

## `let`

Use `let` when a value needs to change within a block.

```js
let count = 0
count += 1
```

## `var`

`var` is function-scoped and hoisted, which makes it surprising in modern code. Prefer `let` and `const` unless you are maintaining legacy code.

## Best practice

- Prefer `const` by default.
- Use `let` only when mutation is required.
- Avoid `var` in new code.

## Related concepts

- [JavaScript introduction](./introduction.md)
- [Function declarations and expressions](./functions.md)
- [Objects and object literal patterns](./objects.md)
