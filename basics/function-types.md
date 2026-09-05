---
id: basics/function-types
title: Types of Functions
type: js-basics
description: Categorize functions by purpose into those that perform a task and those that calculate and return a value.
status: draft
tags:
  - javascript
  - basics
  - fundamentals
  - functions
  - return-values
---

# Types of Functions

In JavaScript, functions can be broadly categorized by their primary purpose into two categories:
1. Functions that **perform a task**
2. Functions that **calculate and return a value**

## 1. Functions that perform a task

These functions execute a sequence of actions or side-effects (such as printing output to the console, showing an alert, or mutating a DOM element):

```js
// Performing a task (printing to console)
function greet(name, lastName) {
  console.log('Hello ' + name + ' ' + lastName);
}

greet('John', 'Smith');
```

When a function does not have an explicit `return` statement, it implicitly returns `undefined`:

```js
let result = greet('John', 'Smith');
console.log(result); // undefined
```

## 2. Functions that calculate a value

These functions compute a calculation and send the result back to the caller using the `return` keyword:

```js
// Calculating a value
function square(number) {
  return number * number;
}

let result = square(2);
console.log(result); // 4
```

Because `square(2)` evaluates to a number (`4`), you can pass the function call directly wherever an expression is expected:

```js
console.log(square(2)); // 4
```

## Function syntaxes in modern JavaScript

Functions can also be written in different syntactic formats:

- **Function declaration**:
  ```js
  function add(a, b) {
    return a + b;
  }
  ```
- **Function expression**:
  ```js
  const add = function (a, b) {
    return a + b;
  };
  ```
- **Arrow function**:
  ```js
  const add = (a, b) => a + b;
  ```

## Related concepts

- [Functions](./functions.md)
- [Variables](./variables.md)
- [Constants](./constants.md)
- [Objects](./objects.md)
- [Arrays](./arrays.md)
