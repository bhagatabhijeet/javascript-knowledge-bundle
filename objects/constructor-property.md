---
id: objects/constructor-property
title: Constructor Property
type: objects
description: Every JavaScript object has a constructor property that references the function used to create it.
status: draft
tags:
  - javascript
  - objects
  - fundamentals
  - constructor-functions
---

# Constructor Property

Every object created in JavaScript has a `constructor` property that points back to the function that constructed it.

```js
function Circle(radius) {
  this.radius = radius;
}

const circle = new Circle(1);
circle.constructor === Circle; // true
```

## Objects and arrays have one too

Object literals and array literals are shorthand for calling the built-in `Object` and `Array` constructors, so they carry the same property:

```js
const obj = {};
obj.constructor === Object; // true

const arr = [];
arr.constructor === Array; // true
```

## Where it comes from

You never assign `constructor` yourself — it lives on the constructor function's `prototype` object and is inherited by every instance through the prototype chain, which is why `circle.constructor` works even though `circle` has no `constructor` property of its own.

## Related concepts

- [Constructor Functions](./constructor-functions.md)
- [Functions are Objects](./functions-are-objects.md)
