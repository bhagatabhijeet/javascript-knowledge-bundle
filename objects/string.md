---
id: objects/string
title: String
type: objects
description: Work with text using string primitives, their built-in methods, and the String wrapper object.
status: draft
tags:
  - javascript
  - objects
  - fundamentals
  - strings
---

# String

A string literal (`'hello'` or `"hello"`) is a primitive value, not an object. However, whenever you call a method on a string, JavaScript temporarily wraps it in a `String` object to give you access to its methods, then discards the wrapper:

```js
const message = 'Hello World';
message.toUpperCase(); // 'HELLO WORLD'
```

## Common string methods

```js
const message = '  Hello World  ';

message.length;            // 16
message.trim();            // 'Hello World'
message.includes('World'); // true
message.indexOf('World');  // 8
message.slice(0, 5).trim(); // 'Hello'
message.split(' ');        // ['', '', 'Hello', 'World', '', '']
```

## Avoid the String constructor

Calling `new String('hello')` creates a `String` **object** rather than a primitive, which behaves unexpectedly when compared:

```js
const a = 'hello';
const b = new String('hello');

typeof a; // 'string'
typeof b; // 'object'
a === b;  // false
```

Always use string literals for everyday text; let JavaScript's automatic wrapping give you access to methods.

## Related concepts

- [Value vs Reference Types](./value-vs-reference-types.md)
- [Template Literal](./template-literals.md)
