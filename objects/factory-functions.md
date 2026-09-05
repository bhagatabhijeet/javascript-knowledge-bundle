---
id: objects/factory-functions
title: Factory Functions
type: objects
description: Create objects without the `new` keyword using a plain function that builds and returns an object literal.
status: draft
tags:
  - javascript
  - objects
  - fundamentals
  - factory-functions
---

# Factory Functions

A **factory function** is a regular function that creates and returns a new object. It avoids repeating the same object literal every time you need a new instance.

```js
function createCircle(radius) {
  return {
    radius,
    draw() {
      console.log('draw');
    }
  };
}

const circle1 = createCircle(1);
const circle2 = createCircle(2);
```

## Why use a factory function

Without it, creating several similar objects means duplicating the same shape by hand:

```js
const circle1 = { radius: 1, draw() { console.log('draw'); } };
const circle2 = { radius: 2, draw() { console.log('draw'); } };
```

A factory function centralizes that shape in one place, so it is defined once and reused for every instance.

## Factory functions vs constructor functions

Both patterns produce new objects with the same shape, but a factory function is called like any other function (`createCircle(1)`), while a [constructor function](./constructor-functions.md) must be invoked with `new` (`new Circle(1)`). Factory functions also have no special relationship with `this` — the object is built explicitly with `return`.

## Related concepts

- [Basics](./basics.md)
- [Constructor Functions](./constructor-functions.md)
- [Functions are Objects](./functions-are-objects.md)
