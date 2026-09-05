---
id: control-flow/if-else
title: If...else
type: control-flow
description: Execute different blocks of code conditionally based on truthy and falsy expressions.
status: draft
tags:
  - javascript
  - control-flow
  - conditionals
  - if-else
---

# If...else

The `if...else` statement is the most common conditional statement in JavaScript. It executes a block of code if a specified condition evaluates to a truthy value.

## Syntax

```js
if (condition) {
  // statement to execute if condition is truthy
} else if (anotherCondition) {
  // statement to execute if anotherCondition is truthy
} else {
  // statement to execute if all previous conditions are falsy
}
```

## Example: Greeting based on time of day

```js
// Hour between 6am and 12pm: Good morning!
// Hour between 12pm and 6pm: Good afternoon!
// Otherwise: Good evening!

let hour = 10;

if (hour >= 6 && hour < 12) {
  console.log('Good morning!');
} else if (hour >= 12 && hour < 18) {
  console.log('Good afternoon!');
} else {
  console.log('Good evening!');
}
```

## Curly braces convention

While single statements can technically be written without curly braces:

```js
// Discouraged:
if (hour >= 6) console.log('Good morning!');
```

It is a widely adopted best practice to always wrap conditional blocks in curly braces `{}` to prevent subtle logic errors when adding additional statements later.

## Related concepts

- [Switch...case](./switch-case.md)
- [The ternary operator](../operators/ternary-operator.md)
- [Comparison operators](../operators/comparison-operators.md)
- [Logical operators](../operators/logical-operators.md)
