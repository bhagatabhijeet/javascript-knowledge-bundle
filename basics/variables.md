---
id: basics/variables
title: Variables
type: js-basics
description: Declare and initialize variables in JavaScript using let, including naming rules and best practices.
status: draft
tags:
  - javascript
  - basics
  - fundamentals
  - variables
---

# Variables

Variables are containers used to store data values in computer memory. In JavaScript, we declare a variable before using it so the runtime allocates space for its value.

## Declaring variables with `let`

In modern JavaScript, declare variables using the `let` keyword:

```js
let name = 'Alice';
console.log(name);
```

You can declare a variable without initializing it immediately; its initial value will be `undefined`:

```js
let interestRate;
console.log(interestRate); // undefined
interestRate = 0.3;
console.log(interestRate); // 0.3
```

## Variable naming rules and conventions

When choosing variable names, follow these essential rules:

1. **Cannot be a reserved keyword**: You cannot name a variable after language keywords (such as `let`, `if`, `const`, `return`).
2. **Should be meaningful**: Avoid single-letter names like `a` or `x`; use descriptive names (e.g., `firstName`, `totalPrice`).
3. **Cannot start with a number**: `let 1name;` is invalid syntax.
4. **Cannot contain spaces or hyphens**: `let first-name;` or `let first name;` causes a syntax error.
5. **CamelCase convention**: By convention, multi-word JavaScript variable names use `camelCase` (the first word is lowercase and subsequent words start with a capital letter, e.g., `firstName`).
6. **Case-sensitive**: `firstName` and `FirstName` are treated as two distinct variables.

## `let` vs `var`

Historically, JavaScript used `var` to declare variables:

```js
var legacyName = 'Alice';
```

However, `var` is function-scoped and hoisted, which frequently causes subtle scope leaks and bugs. Modern JavaScript standardizes on block-scoped `let` and `const`.

## Related concepts

- [Constants](./constants.md)
- [Primitive data types](./primitive-types.md)
- [Dynamic typing and type coercion](./dynamic-typing.md)
- [Objects](./objects.md)
- [Arrays](./arrays.md)
- [Functions](./functions.md)
- [What is JavaScript](../getting-started/what-is-javascript.md)
