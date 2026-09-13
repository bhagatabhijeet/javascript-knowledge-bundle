---
id: objects/builtin-objects/string
title: String
type: objects
description: Work with text using string primitives, their built-in methods, and the String wrapper object.
status: draft
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/String
    title: "String - MDN Web Docs"
tags:
  - javascript
  - objects
  - fundamentals
  - strings
  - builtin-objects
---

# String

A string literal (`'hello'`, `"hello"`, or `` `hello` ``) is a **primitive** value, not an object — `typeof 'hello'` is `'string'`. However, whenever you call a method on a string primitive, JavaScript temporarily wraps it in a `String` **object** (a process called autoboxing) to give you access to its methods, calls the method, then discards the wrapper:

```js
const message = 'Hello World';
message.toUpperCase(); // 'HELLO WORLD' — JS briefly boxes `message` as a String object to run this
```

## Strings are immutable

Every string method returns a **new** string; none of them modify the original:

```js
const message = 'hello';
message.toUpperCase(); // 'HELLO'
message;                // still 'hello' — unchanged
```

To keep a transformed value, you have to assign it: `message = message.toUpperCase();`.

## Common string methods

```js
const message = '  Hello World  ';

message.length;             // 16
message.trim();             // 'Hello World'
message.includes('World');  // true
message.startsWith('  He'); // true
message.indexOf('World');   // 8
message.slice(2, 7);        // 'Hello'
message.split(' ');         // ['', '', 'Hello', 'World', '', '']
message.replace('World', 'There'); // '  Hello There  '
message.trim().padStart(15, '*');  // '****Hello World'
```

Because every method returns a new string, calls can be chained:

```js
'  hello world  '.trim().toUpperCase().slice(0, 5); // 'HELLO'
```

### Frequently used methods at a glance

| Method | What it does |
| --- | --- |
| `charAt(i)` / `at(i)` | Character at index `i` (`at` also accepts negative indices, counting from the end) |
| `indexOf()` / `lastIndexOf()` | Index of the first/last occurrence of a substring, or `-1` if not found |
| `includes()` / `startsWith()` / `endsWith()` | Whether the string contains, starts with, or ends with a substring |
| `slice(start, end)` | Extracts a substring; supports negative indices |
| `split(separator)` | Splits the string into an array of substrings |
| `trim()` / `trimStart()` / `trimEnd()` | Removes whitespace from both ends, or just one |
| `toUpperCase()` / `toLowerCase()` | Case conversion |
| `replace()` / `replaceAll()` | Replaces the first (or every) match with another string |
| `padStart()` / `padEnd()` | Pads the string to a target length |
| `repeat(count)` | Repeats the string `count` times |

## Avoid the `String` constructor

Calling `new String('hello')` creates a `String` **object** rather than a primitive, which behaves unexpectedly when compared:

```js
const a = 'hello';
const b = new String('hello');

typeof a; // 'string'
typeof b; // 'object'
a === b;  // false — a primitive is never === an object, even with the same text
```

Always use string literals for everyday text, and let JavaScript's automatic wrapping give you access to methods when you need them.

## Related concepts

- [Value vs Reference Types](../value-vs-reference-types.md)
- [Template Literal](../template-literals.md)
- [Math](./math.md)
