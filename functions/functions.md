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

A function expression defines a function the same way you'd assign any other value — a number, a string, an object — to a variable or constant. That's possible because [functions are objects](../objects/functions-are-objects.md):

```js
const run = function () {
  console.log('run');
};

run(); // Must be called after definition (not hoisted)
```

Because this is a variable declaration, not a standalone statement, it ends with a semicolon — unlike a function declaration, which doesn't need one. Leaving it off doesn't cause an error, but by convention function expressions are terminated like any other assignment.

### Anonymous vs. named function expressions

The function on the right-hand side has no name of its own here — it's an **anonymous function expression**. You can optionally give it one, making it a **named function expression**:

```js
const run = function runner() {
  console.log('run');
};
```

Either way, you still call it through the variable it's assigned to (`run()`), not through the function's own name.

### One function, multiple references

Since `run` holds a reference to a function object, assigning it to another variable doesn't create a copy — both variables point at the exact same function:

```js
const run = function () {
  console.log('run');
};

const move = run; // move references the same function object as run

run();  // 'run'
move(); // 'run' — same function, called through a different variable
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
- [Functions are Objects](../objects/functions-are-objects.md)
- [Hoisting](./hoisting.md)
- [Objects](../objects/objects.md)
- [Arrays](../arrays/)
