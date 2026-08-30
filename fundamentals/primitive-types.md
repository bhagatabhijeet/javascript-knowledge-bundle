---
id: fundamentals/primitive-types
title: Primitive data types
type: Concept
description: The seven primitive types in JavaScript and how they behave as immutable values compared to objects.
status: review
trust: machine-assisted
stale: false
tags:
  - javascript
  - fundamentals
  - types
  - primitives
---

# Primitive data types

JavaScript has seven primitive types. A primitive is immutable and compared by value, not by reference.

```js
typeof 'hello'     // 'string'
typeof 42          // 'number'
typeof true        // 'boolean'
typeof undefined   // 'undefined'
typeof Symbol('id') // 'symbol'
typeof 10n         // 'bigint'
typeof null        // 'object' (a long-standing language quirk)
```

## The seven primitives

- **string** — text, written with quotes or backticks: `'hi'`, `"hi"`, `` `hi ${name}` ``.
- **number** — all numeric values, including floats: `42`, `3.14`, `NaN`, `Infinity`.
- **boolean** — `true` or `false`.
- **undefined** — a variable that has been declared but not assigned a value.
- **null** — an explicit "no value," assigned intentionally.
- **symbol** — a unique, immutable identifier, often used as an object property key.
- **bigint** — integers larger than `Number.MAX_SAFE_INTEGER`, written with an `n` suffix: `10n`.

## Immutability and comparison by value

Primitives cannot be mutated in place, and operations that seem to change them actually produce new values.

```js
let a = 'hello'
a.toUpperCase() // returns 'HELLO', but does not change `a`
console.log(a)  // 'hello'

let x = 5
let y = x
y = 10
console.log(x) // 5, unaffected by reassigning y
```

Two primitives with the same value are equal, even though they are separate pieces of memory:

```js
'hi' === 'hi' // true
5 === 5       // true
```

## Primitives vs objects

Objects (including arrays and functions) are reference types: variables hold a pointer to shared, mutable data rather than the data itself.

```js
const obj1 = { count: 1 }
const obj2 = obj1
obj2.count = 2
console.log(obj1.count) // 2, both variables reference the same object
```

## Related concepts

- [Variables and declarations](./variables.md)
- [Dynamic typing and type coercion](./dynamic-typing.md)
- [Objects and object literal patterns](./objects.md)
- [Arrays](./arrays.md)

## Sources

- https://developer.mozilla.org/en-US/docs/Glossary/Primitive
- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Data_structures

This draft was generated from general knowledge of MDN's JavaScript documentation and has not been checked against a live source. It should receive human review before its status or trust is promoted.
