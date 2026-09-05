---
id: basics/functions
title: Functions
type: js-basics
description: Define reusable blocks of logic using function declarations, parameters, and arguments.
status: draft
tags:
  - javascript
  - basics
  - fundamentals
  - functions
---

# Functions

A **function** is a fundamental building block in JavaScript. It is a reusable block of statements designed to perform a specific task or calculate a value.

## Declaring and invoking a function

Declare a function using the `function` keyword, followed by the function name, parentheses `()`, and curly braces `{}` containing the function body:

```js
// Declaration
function greet() {
  console.log('Hello World');
}

// Invocation (call)
greet(); // Output: Hello World
```

## Parameters vs. arguments

Functions become flexible when they accept input:

- A **parameter** is the variable listed in the function definition.
- An **argument** is the actual value supplied to the function when it is invoked.

```js
// 'name' is a parameter
function greet(name) {
  console.log('Hello ' + name);
}

// 'John' and 'Mary' are arguments
greet('John'); // Hello John
greet('Mary'); // Hello Mary
```

### Multiple parameters

You can define multiple parameters separated by commas:

```js
function greet(firstName, lastName) {
  console.log('Hello ' + firstName + ' ' + lastName);
}

greet('John', 'Smith'); // Hello John Smith
```

If you omit an argument when calling a function, that parameter defaults to `undefined`:

```js
greet('John'); // Hello John undefined
```

## Related concepts

- [Types of Functions](./function-types.md)
- [Variables](./variables.md)
- [Constants](./constants.md)
- [Objects](./objects.md)
- [Arrays](./arrays.md)
