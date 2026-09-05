---
id: basics/dynamic-typing
title: Dynamic Types
type: js-basics
description: How JavaScript determines variable types at runtime dynamically and how to inspect types using the typeof operator.
status: draft
tags:
  - javascript
  - basics
  - fundamentals
  - types
  - dynamic-typing
---

# Dynamic Types

Programming languages fall into two categories when handling types:
1. **Static languages**: The type of a variable is fixed at compile time and cannot change (e.g., C++, Java, C#).
   ```text
   string name = 'John'; // In a static language, name must always hold a string
   ```
2. **Dynamic languages**: The type of a variable is determined at runtime based on the value currently assigned to it, and it can change dynamically over time.

JavaScript is a **dynamic language**. Variables do not have types; values have types.

## Dynamic typing in action

You can assign a string to a variable, and later assign a number or boolean to the same variable:

```js
let name = 'Alice'; // type is string
console.log(typeof name); // "string"

name = 1;          // reassign to number; type dynamically changes
console.log(typeof name); // "number"
```

## Inspecting types with `typeof`

The `typeof` operator returns a string representing the current type of an operand:

```js
let name = 'Alice';        // string
let age = 30;             // number
let isApproved = false;   // boolean
let firstName = undefined;// undefined
let selectedColor = null; // object (historical JavaScript quirk)

console.log(typeof name);          // "string"
console.log(typeof age);           // "number"
console.log(typeof isApproved);    // "boolean"
console.log(typeof firstName);     // "undefined"
console.log(typeof selectedColor); // "object"
```

> [!NOTE]
> In JavaScript, `typeof null` returns `"object"`. This is a well-known historical bug from the initial version of JavaScript in 1995 that is preserved for backwards compatibility.

## Related concepts

- [Variables](./variables.md)
- [Constants](./constants.md)
- [Primitive Types](./primitive-types.md)
- [Objects](./objects.md)
- [Arrays](./arrays.md)
- [Functions](./functions.md)
