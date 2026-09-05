---
id: objects/functions-are-objects
title: Functions are Objects
type: objects
description: JavaScript functions are first-class objects with their own properties, methods, and constructor.
status: draft
tags:
  - javascript
  - objects
  - fundamentals
  - functions
---

# Functions are Objects

In JavaScript, functions are a special kind of object. Like any object, they can have properties, be passed around as values, and are themselves created by a constructor (`Function`).

```js
function Circle(radius) {
  this.radius = radius;
}

typeof Circle; // 'function'
Circle instanceof Object; // true
```

## Built-in properties and methods

Because a function is an object, it comes with useful members such as `name`, `length`, `call`, `apply`, and `bind`:

```js
Circle.name;   // 'Circle'
Circle.length; // 1 (number of declared parameters)

const another = {};
Circle.call(another, 10); // invoke Circle with `this` set to `another`
another.radius; // 10
```

## Attaching your own properties

You can also attach custom properties directly to a function object:

```js
Circle.callCount = 0;
```

## Related concepts

- [Constructor Functions](./constructor-functions.md)
- [Constructor Property](./constructor-property.md)
- [Value vs Reference Types](./value-vs-reference-types.md)
