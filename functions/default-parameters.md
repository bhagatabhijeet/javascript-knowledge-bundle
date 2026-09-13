---
id: functions/default-parameters
title: Default Parameters
type: functions
description: Give a parameter a fallback value with = defaultValue, used only when the caller omits that argument or passes undefined.
status: draft
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Functions/Default_parameters
    title: "Default parameters - MDN Web Docs"
tags:
  - javascript
  - functions
  - default-parameters
  - es6
  - fundamentals
---

# Default Parameters

A parameter can be given a fallback value right in the function's signature, using `= defaultValue`. It's used whenever the caller leaves that argument out entirely:

```js
function greet(name = 'stranger') {
  console.log(`Hello, ${name}!`);
}

greet('Alice'); // Hello, Alice!
greet();        // Hello, stranger!
```

This replaces the older pattern of checking for a missing argument inside the function body:

```js
function greet(name) {
  name = name === undefined ? 'stranger' : name;
  console.log(`Hello, ${name}!`);
}
```

## Only `undefined` triggers the default

The default kicks in specifically when the argument is `undefined` — either because it was omitted, or because `undefined` was passed explicitly. Any other falsy value, including `null`, `''`, or `0`, is used as-is:

```js
greet(undefined); // Hello, stranger! — same as omitting it
greet(null);      // Hello, null! — null is a real value, the default is not used
```

This is the same rule the [rest operator and `arguments`](./functions.md) apply for a missing argument — `undefined` is JavaScript's way of representing "nothing was passed here."

## Default values are computed at call time

The default expression isn't evaluated once when the function is defined — it runs fresh on every call that needs it:

```js
function append(value, array = []) {
  array.push(value);
  return array;
}

append(1); // [1]
append(2); // [2] — a brand-new array, not [1, 2]
```

Because a fresh `[]` is created on every call that omits `array`, callers never accidentally share state through a stale default value.

## A default can reference earlier parameters

Default expressions can use any parameter declared before them in the list:

```js
function greet(name, greeting = `Hello, ${name}`) {
  console.log(greeting);
}

greet('Alice');        // Hello, Alice
greet('Alice', 'Hi');   // Hi
```

A default can't reference a parameter declared *after* it, or a variable declared inside the function body — only what's already in scope by that point in the parameter list.

## Parameters with defaults don't count toward `length`

A function's `length` property reports the number of parameters *before* the first one with a default (or a rest parameter). Once a parameter has a default, it — and everything after it — is considered optional and excluded from the count:

```js
function greet(name, greeting = 'Hello') {}

greet.length; // 1 — only `name` is counted
```

## Related concepts

- [Function declarations and expressions](./functions.md)
- [Rest Operator](./rest-operator.md)
- [Arrow Functions](./arrow-functions.md)
