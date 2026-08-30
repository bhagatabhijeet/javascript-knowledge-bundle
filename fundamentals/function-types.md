---
id: fundamentals/function-types
title: Types of functions
type: js-basics
description: The different ways to define and categorize functions in JavaScript, from declarations to higher-order and async functions.
status: draft
tags:
  - javascript
  - fundamentals
  - functions
  - types
generated: { by: claude/sonnet-5, at: 2026-08-29T00:00:00Z }
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/function*
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/async_function
---

# Types of functions

JavaScript functions can be categorized by how they are defined and how they are used. See [Function declarations and expressions](./functions.md) for the basics of declarations, expressions, and arrow functions.

## Named vs anonymous functions

```js
function greet() {}          // named
const greet2 = function () {} // anonymous, assigned to a variable
const greet3 = () => {}       // arrow functions are always anonymous unless assigned
```

A named function shows its name in stack traces, which helps debugging.

## Immediately Invoked Function Expressions (IIFE)

An IIFE runs as soon as it is defined, often used to create an isolated scope.

```js
(function () {
  console.log('runs immediately')
})()
```

## Methods

A function stored as an object property is a method. Inside a regular method, `this` refers to the object it was called on.

```js
const counter = {
  count: 0,
  increment() {
    this.count += 1
  },
}
counter.increment()
```

Arrow functions do not bind their own `this` and are usually avoided for object methods that rely on `this`.

## Constructor functions

A function invoked with `new` builds an object. By convention, constructor names are capitalized.

```js
function Person(name) {
  this.name = name
}
const alice = new Person('Alice')
```

Modern code generally prefers `class` syntax, which is largely sugar over this pattern.

## Higher-order functions

A higher-order function takes a function as an argument, returns a function, or both.

```js
function withLogging(fn) {
  return (...args) => {
    console.log('calling with', args)
    return fn(...args)
  }
}

const loggedAdd = withLogging((a, b) => a + b)
```

Array methods like `map`, `filter`, and `reduce` are higher-order functions: see [Arrays](./arrays.md).

## Callback functions

A callback is a function passed into another function to be invoked later, either synchronously or asynchronously.

```js
setTimeout(() => console.log('later'), 1000) // asynchronous callback
[1, 2, 3].forEach((n) => console.log(n))      // synchronous callback
```

## Generator functions

A generator can pause and resume execution, yielding a sequence of values over time.

```js
function* countUp() {
  yield 1
  yield 2
  yield 3
}
const iterator = countUp()
iterator.next() // { value: 1, done: false }
```

## Async functions

An `async` function always returns a promise and lets you use `await` inside it. See [Async JavaScript](./async.md) for the full event-loop and promise model.

```js
async function fetchData() {
  const response = await fetch('/api/data')
  return response.json()
}
```

## Related concepts

- [Function declarations and expressions](./functions.md)
- [Async JavaScript](./async.md)
- [Arrays](./arrays.md)
- [Objects and object literal patterns](./objects.md)

This draft was generated from general knowledge of MDN's JavaScript documentation and has not been checked against a live source. It should receive human review before its status is promoted or a `verified` entry is added.
