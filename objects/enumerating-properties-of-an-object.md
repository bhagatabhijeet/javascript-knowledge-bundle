---
id: objects/enumerating-properties-of-an-object
title: Enumerating Properties of an Object
type: objects
description: List an object's keys, values, or entries using for...in, Object.keys, Object.values, and Object.entries.
status: draft
tags:
  - javascript
  - objects
  - fundamentals
  - iteration
---

# Enumerating Properties of an Object

JavaScript provides several ways to loop over or extract an object's properties.

## for...in loop

Iterates over the enumerable property **keys** of an object, including inherited ones:

```js
const circle = { radius: 1, color: 'yellow' };

for (let key in circle) {
  console.log(key, circle[key]);
}
```

## Object.keys()

Returns an array of an object's own enumerable keys:

```js
Object.keys(circle); // ['radius', 'color']
```

## Object.values()

Returns an array of an object's own enumerable values:

```js
Object.values(circle); // [1, 'yellow']
```

## Object.entries()

Returns an array of `[key, value]` pairs, useful for destructuring in a loop:

```js
for (const [key, value] of Object.entries(circle)) {
  console.log(key, value);
}
```

## Related concepts

- [Dynamic Nature of Objects](./dynamic-nature-of-objects.md)
- [Cloning an Object](./cloning-an-object.md)
- [For...in](../control-flow/for-in.md)
