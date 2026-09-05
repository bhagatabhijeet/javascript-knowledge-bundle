---
id: functions/functions
title: Function declarations and expressions
type: functions
description: Learn the primary ways to define functions and how hoisting and closures change behavior.
status: draft
tags:
  - javascript
  - functions
  - fundamentals
---

# Function declarations and expressions

Functions are the building blocks of readable and maintainable JavaScript programs. They encapsulate reusable logic and can be passed around as first-class values.

## Function declaration

A function declaration starts with the `function` keyword and has a name:

```js
function walk() {
  console.log('walk');
}
```

Function declarations are **hoisted** to the top of their execution context, meaning you can call them before they are defined.

## Function expression

A function expression defines a function and assigns it to a variable or constant:

```js
// Anonymous function expression
const run = function() {
  console.log('run');
};

run(); // Must be called after definition (not hoisted)
```

## Arguments and the `arguments` object

Functions can inspect the special `arguments` object to handle a varying number of arguments:

```js
function sum() {
  let total = 0;
  for (let value of arguments) {
    total += value;
  }
  return total;
}

console.log(sum(1, 2, 3, 4)); // 10
```

## Rest operator (`...`)

In modern JavaScript, the rest operator is preferred over `arguments`:

```js
function sum(...args) {
  return args.reduce((a, b) => a + b);
}

console.log(sum(1, 2, 3, 4)); // 10
```

## Related concepts

- [Types of functions](./function-types.md)
- [Objects](../objects/objects.md)
- [Arrays](../arrays/arrays.md)
