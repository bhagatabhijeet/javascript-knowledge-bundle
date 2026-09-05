---
id: objects/dynamic-nature-of-objects
title: Dynamic Nature of Objects
type: objects
description: Add, modify, and delete properties on a JavaScript object at any time, even after it has been created.
status: draft
tags:
  - javascript
  - objects
  - fundamentals
  - dynamic-typing
---

# Dynamic Nature of Objects

Unlike statically-typed languages, JavaScript objects are **dynamic** — you are not locked into a fixed set of properties once an object is created.

```js
const circle = { radius: 1 };
```

## Adding properties

Assign to a new property name with dot or bracket notation, and JavaScript creates it:

```js
circle.color = 'yellow';
circle.draw = function () {
  console.log('draw');
};
```

## Removing properties

Use the `delete` operator to remove a property entirely:

```js
delete circle.color;
```

## Checking whether a property exists

```js
'color' in circle;              // false (after delete above)
circle.hasOwnProperty('radius'); // true
```

The `in` operator checks the object and its prototype chain, while `hasOwnProperty` checks only properties defined directly on the object.

## Related concepts

- [Basics](./basics.md)
- [Enumerating Properties of an Object](./enumerating-properties-of-an-object.md)
- [Cloning an Object](./cloning-an-object.md)
