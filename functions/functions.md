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

## The parameter count is just a suggestion

Since JavaScript is dynamically typed, that flexibility extends to how many arguments you pass — the engine never enforces a match with the declared parameter list:

```js
function sum(a, b) {
  return a + b;
}

sum(1, 2);       // 3
sum(1);          // NaN — b is undefined, and 1 + undefined is not a number
sum();           // NaN — both a and b are undefined
sum(1, 2, 3, 4, 5); // 3 — the extra arguments are accepted, just never used
```

Passing too few or too many arguments is never an error in JavaScript; it just changes what ends up inside the function.

## Arguments and the `arguments` object

Every regular function has access to a special `arguments` object holding every argument it was actually called with, regardless of how many parameters were declared:

```js
function sum(a, b) {
  console.log(arguments);
  return a + b;
}

sum(1, 2, 3, 4, 5);
// Arguments(5) [1, 2, 3, 4, 5, callee: f, Symbol(Symbol.iterator): f]
```

`arguments` looks like an array — it has indexed properties (`0`, `1`, `2`, ...) and a `length` — but it's **not** a real `Array`: it has no `map`, `filter`, or `reduce`. It does have a `Symbol.iterator`, though, which is what makes it possible to loop over with [`for...of`](../control-flow/for-of.md):

```js
function sum() {
  let total = 0;
  for (let value of arguments) {
    total += value;
  }
  return total;
}

console.log(sum(1, 2, 3, 4, 5)); // 15
```

Because the function reads everything through `arguments` instead of named parameters, the parameter list can be dropped entirely — `sum()` works exactly the same as `sum(a, b)` would have, but now accepts any number of arguments.

`arguments` also exposes a `callee` property referencing the currently-executing function itself — but avoid it: `callee` is disallowed in strict-mode code (which ES modules and classes use by default) precisely because relying on it makes functions harder to optimize and refactor.

The [rest operator](./rest-operator.md) is the modern replacement for this whole pattern — it does the same job with an actual array.

## Related concepts

- [Types of functions](./function-types.md)
- [Functions are Objects](../objects/functions-are-objects.md)
- [Hoisting](./hoisting.md)
- [Rest Operator](./rest-operator.md)
- [Default Parameters](./default-parameters.md)
- [Objects](../objects/objects.md)
- [Arrays](../arrays/)
