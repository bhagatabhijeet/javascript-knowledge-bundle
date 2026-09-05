---
id: basics/objects
title: Objects
type: js-basics
description: Work with reference types using JavaScript object literals, dot notation, and bracket notation.
status: draft
tags:
  - javascript
  - basics
  - fundamentals
  - objects
  - reference-types
---

# Objects

When dealing with multiple related variables, declaring them individually becomes unwieldy:

```js
let name = 'Alice';
let age = 30;
```

An **object** in JavaScript is a reference type that groups related properties (key-value pairs) together into a single entity.

## Object literal syntax

Create an object using curly braces `{}` (object literal syntax):

```js
let person = {
  name: 'Alice',
  age: 30
};

console.log(person);
```

The keys (`name`, `age`) are the properties of the object, and `'Alice'` and `30` are their respective values.

## Accessing and modifying properties

JavaScript provides two ways to read or modify an object's properties:

### 1. Dot notation (preferred default)

Dot notation is clean, concise, and the standard choice:

```js
// Reading a property
console.log(person.name); // 'Alice'

// Updating a property
person.name = 'John';
console.log(person.name); // 'John'
```

### 2. Bracket notation (for dynamic property access)

Bracket notation uses square brackets with the property key as a string:

```js
// Reading via bracket notation
console.log(person['name']); // 'John'

// Updating via bracket notation
person['name'] = 'Mary';
```

Bracket notation is indispensable when:
- The property name is determined dynamically at runtime:
  ```js
  let selection = 'name';
  person[selection] = 'Mary';
  ```
- The property key contains characters not valid in identifiers (e.g. spaces or hyphens): `person['first-name']`.

## Related concepts

- [Variables](./variables.md)
- [Constants](./constants.md)
- [Primitive Types](./primitive-types.md)
- [Arrays](./arrays.md)
- [Functions](./functions.md)
