---
id: objects/template-literals
title: Template Literal
type: objects
description: Build strings with embedded expressions and multi-line text using backtick template literals.
status: draft
tags:
  - javascript
  - objects
  - fundamentals
  - strings
---

# Template Literal

A **template literal** is a string delimited with backticks (`` ` ``) instead of quotes. It supports embedded expressions and multi-line text without special escape characters.

## String interpolation

Embed any expression inside `${}`:

```js
const name = 'Alice';
const age = 30;

const message = `${name} is ${age} years old.`;
```

This replaces older, more error-prone string concatenation:

```js
const message = name + ' is ' + age + ' years old.'; // equivalent, harder to read
```

## Multi-line strings

Template literals preserve line breaks written directly in the source:

```js
const message = `
  Hello ${name},
  Welcome!
`;
```

## Related concepts

- [String](./string.md)
- [Basics](./basics.md)
