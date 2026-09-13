---
id: objects/template-literals
title: Template Literal
type: objects
description: Build strings with embedded expressions and multi-line text using backtick template literals.
status: draft
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals
    title: "Template literals (Template strings) - MDN Web Docs"
tags:
  - javascript
  - objects
  - fundamentals
  - strings
---

# Template Literal

A **template literal** is a string delimited with backticks (`` ` ``) instead of quotes. It supports embedded expressions and multi-line text without special escape characters.

This is a syntax feature for building `string` values — it isn't a built-in object like [Math, String, or Date](./builtin-objects/), which is why it lives alongside them rather than inside that folder.

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

Note one subtle difference: `${}` always coerces its expression directly to a string, while `+` first coerces operands to primitives — the two can occasionally produce different results with unusual values (e.g. objects with custom `valueOf`/`toString` behavior).

## Multi-line strings

Template literals preserve line breaks written directly in the source, with no `\n` needed:

```js
const message = `
  Hello ${name},
  Welcome!
`;
```

## Nesting template literals

A template literal can be nested inside another template literal's `${}`, which is handy for inline conditionals:

```js
const isLargeScreen = false;
const label = `header ${isLargeScreen ? '' : `(${name})`}`;
```

## Escaping backticks and `${`

To include a literal backtick or `${` inside a template literal, escape it with a backslash:

```js
`` \` `` === '`';   // true
`\${1}` === '${1}'; // true — the `${` is not treated as interpolation
```

## Tagged templates

Prefixing a template literal with a function name — with no parentheses — calls that function as a **tag**, passing it the literal string pieces and the interpolated values separately, so it can process them itself:

```js
function upperTag(strings, ...values) {
  return strings.reduce(
    (result, str, i) => `${result}${str}${(values[i] ?? '').toString().toUpperCase()}`,
    ''
  );
}

upperTag`Hello ${name}, you are ${age} years old.`;
// 'Hello ALICE, you are 30 years old.'
```

This is how libraries like styled-components and tagged SQL/GraphQL helpers parse template literals as their own mini-syntax rather than treating them as plain strings.

## Related concepts

- [Built-in Objects (Math, String, Date)](./builtin-objects/)
- [String](./builtin-objects/string.md)
- [Joining Arrays](../arrays/joining-arrays.md)
- [Basics](./basics.md)
