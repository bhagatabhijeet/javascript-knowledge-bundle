---
id: basics/primitive-types
title: Primitive Types
type: js-basics
description: The primitive types in JavaScript (string, number, boolean, undefined, null, symbol, bigint) and their value semantics.
status: draft
tags:
  - javascript
  - basics
  - fundamentals
  - types
  - primitives
---

# Primitive Types

JavaScript divides values into two broad categories:
1. **Primitives** (Value types)
2. **Reference Types** (Objects, Arrays, Functions)

A primitive value represents data at the lowest level of the language implementation. Primitives are immutable and compared by value.

## Common primitive types

In everyday JavaScript, five primitives are most commonly used:

- **String**: Textual data enclosed in quotes:
  ```js
  let name = 'Alice';
  ```
- **Number**: Numeric values (integers and floating-point numbers):
  ```js
  let age = 30;
  let rate = 0.5;
  ```
- **Boolean**: Logical flags with values `true` or `false`:
  ```js
  let isApproved = true;
  ```
- **undefined**: A variable declared without an assigned value, or explicitly set to `undefined`:
  ```js
  let firstName = undefined;
  ```
- **null**: Represents the intentional absence of any value:
  ```js
  let selectedColor = null;
  ```

Modern JavaScript also includes two advanced primitive types:
- **Symbol**: Used to create unique, anonymous object property identifiers.
- **BigInt**: Represents arbitrary-precision integers larger than $2^{53} - 1$ (`10n`).

## Primitives are compared by value

Two primitives with identical values are strictly equal:

```js
'hello' === 'hello'; // true
42 === 42;           // true
```

Operations on primitives always produce new values rather than mutating the existing one:

```js
let greeting = 'hello';
greeting.toUpperCase(); // returns 'HELLO'
console.log(greeting);  // 'hello' (original string unchanged)
```

## Related concepts

- [Variables](./variables.md)
- [Constants](./constants.md)
- [Dynamic typing and type coercion](./dynamic-typing.md)
- [Objects](./objects.md)
- [Arrays](./arrays.md)
