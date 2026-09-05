---
id: objects/basics
title: Basics
type: objects
description: Understand object literals, grouping related properties and methods into objects.
status: draft
tags:
  - javascript
  - objects
  - fundamentals
---

# Object Basics

Objects in JavaScript are collections of key-value pairs used to model real-world concepts and group related data and functionality together.

If a function is part of an object, it is called a **method**.

## Object literal syntax

The simplest way to create an object is using object literal syntax `{}`:

```js
const circle = {
  radius: 1,
  location: {
    x: 1,
    y: 1
  },
  isVisible: true,
  draw: function() {
    console.log('draw circle');
  }
};

circle.draw(); // Calling a method
```

## Reading and updating properties

- **Dot notation**: `circle.radius = 2;` (concise and standard).
- **Bracket notation**: `circle['radius'] = 2;` (useful when property names are dynamic).

## Related concepts

- [Factory Functions](./factory-functions.md)
- [Constructor Functions](./constructor-functions.md)
- [Dynamic Nature of Objects](./dynamic-nature-of-objects.md)
