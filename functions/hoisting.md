---
id: functions/hoisting
title: Hoisting
type: functions
description: JavaScript moves declarations to the top of their scope before running any code, which changes what you can safely use before it's written.
status: draft
tags:
  - javascript
  - functions
  - hoisting
  - scope
  - fundamentals
---

# Hoisting

Before running a script, the JavaScript engine scans it and registers every declaration it finds, in the current scope, ahead of time. This is called **hoisting** — it's as if declarations were physically moved ("hoisted") to the top of their scope, even though the code you wrote never actually moved.

Hoisting doesn't work the same way for every kind of declaration, and mixing them up is one of the most common sources of confusing bugs for JavaScript beginners.

## Function declarations are fully hoisted

A function declared with the `function` keyword is hoisted **with its entire body**, so it can be called before the line where it's written:

```js
sayHello(); // 'Hello!' — works fine

function sayHello() {
  console.log('Hello!');
}
```

## `var` is hoisted, but only the declaration

A variable declared with `var` is hoisted too, but only the *declaration* — its assignment stays where you wrote it. Before that line runs, the variable already exists, initialized to `undefined`:

```js
console.log(name); // undefined — `name` exists, but isn't assigned yet
var name = 'Alice';
console.log(name); // Alice
```

This is effectively the same as if the code had been rewritten like this:

```js
var name;        // declaration hoisted to the top
console.log(name); // undefined
name = 'Alice';   // assignment stays in place
console.log(name); // Alice
```

## `let` and `const` are hoisted into a "temporal dead zone"

`let` and `const` are hoisted too, but the engine does not initialize them to `undefined`. They stay in a **temporal dead zone (TDZ)** — accessible in name only — from the top of the scope until the line that declares them runs. Touching them before that throws an error instead of silently returning `undefined`:

```js
console.log(age); // ReferenceError: Cannot access 'age' before initialization
let age = 25;
```

This is generally considered a feature, not a limitation: it turns a silent `undefined` bug (with `var`) into a loud, immediate error that points straight at the problem.

## Function expressions and arrow functions are not hoisted like declarations

Only *function declarations* get their whole body hoisted. A function assigned to a `var`, `let`, or `const` is hoisted the same way that variable is — which means the function itself isn't usable until its assignment line actually runs:

```js
sayHi(); // TypeError: sayHi is not a function (var hoisted, but still undefined at this point)

var sayHi = function () {
  console.log('Hi!');
};
```

```js
sayBye(); // ReferenceError: Cannot access 'sayBye' before initialization (TDZ)

const sayBye = () => {
  console.log('Bye!');
};
```

## Why this matters

- Relying on hoisting to call a function before its declaration is fine for `function` declarations — it's a normal, documented part of the language.
- Relying on it for `var` variables is a common source of bugs: code appears to work while actually reading `undefined` instead of the intended value.
- `let` and `const`'s TDZ behavior is one of the reasons modern JavaScript style guides recommend them over `var` — mistakes surface immediately as errors instead of silently producing `undefined`.

## Related concepts

- [Function declarations and expressions](./functions.md)
- [Variable Declaration: var, let, and const](../basics/variable-declaration.md)
- [Variables](../basics/variables.md)
- [Constants](../basics/constants.md)
