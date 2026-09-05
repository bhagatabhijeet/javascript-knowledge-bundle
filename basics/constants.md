---
id: basics/constants
title: Constants
type: js-basics
description: Declare non-reassignable identifiers using the const keyword, and understand when to use const vs let.
status: draft
tags:
  - javascript
  - basics
  - fundamentals
  - constants
---

# Constants

In many programming scenarios, you want a variable's value to remain fixed and never be accidentally overwritten. JavaScript provides the `const` keyword to declare **constants**.

## Declaring a constant

Declare a constant using `const`. You **must** initialize a constant at the time of declaration:

```js
const interestRate = 0.3;
console.log(interestRate); // 0.3
```

Attempting to reassign a constant results in a runtime error:

```js
const interestRate = 0.3;
interestRate = 1; // TypeError: Assignment to constant variable.
```

## When to use `const` vs. `let`

Follow this practical rule of thumb:

- **Default to `const`**: Use `const` for every identifier by default. It communicates clear intent that the binding will never change and prevents accidental reassignment bugs.
- **Use `let` only when reassignment is required**: Use `let` when you know a value must be modified later (such as a counter in a loop or an accumulator).

## `const` and reference types (Objects & Arrays)

A common point of confusion: `const` prevents **reassigning the variable identifier**, but it does not make the underlying object or array immutable.

```js
const person = { name: 'Alice' };

// Permitted: mutating an object property
person.name = 'John';
console.log(person.name); // 'John'

// Error: reassigning the variable identifier itself
person = { name: 'Bob' }; // TypeError: Assignment to constant variable.
```

## Related concepts

- [Variables](./variables.md)
- [Primitive data types](./primitive-types.md)
- [Dynamic typing and type coercion](./dynamic-typing.md)
- [Objects](./objects.md)
- [Arrays](./arrays.md)
