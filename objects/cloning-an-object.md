---
id: objects/cloning-an-object
title: Cloning an Object
type: objects
description: Copy an object's properties into a new object using Object.assign, the spread operator, or structuredClone.
status: draft
tags:
  - javascript
  - objects
  - fundamentals
  - reference-types
---

# Cloning an Object

Because objects are [reference types](./value-vs-reference-types.md), assigning one variable to another does not create a copy. To get an independent copy, you need to clone it explicitly.

## Object.assign()

Copies the own enumerable properties of one or more source objects into a target object:

```js
const circle = { radius: 1, color: 'yellow' };
const clone = Object.assign({}, circle);
```

## Spread operator

A more concise, modern equivalent:

```js
const clone = { ...circle };
```

Both `Object.assign` and the spread operator perform a **shallow** clone: nested objects are still shared by reference between the original and the clone.

## Deep cloning

To copy nested objects as well, use `structuredClone`, available in modern JavaScript runtimes:

```js
const deepClone = structuredClone(circle);
```

An older workaround using `JSON.parse(JSON.stringify(circle))` also produces a deep clone, but silently drops values `JSON` cannot represent, such as functions, `undefined`, and `Date` objects (which are converted to strings).

## Related concepts

- [Value vs Reference Types](./value-vs-reference-types.md)
- [Enumerating Properties of an Object](./enumerating-properties-of-an-object.md)
