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

When JavaScript runs a script, it doesn't just execute your code top to bottom in a single pass. First it creates an **execution context** in two phases: a **memory creation phase**, where the engine scans the whole scope and sets aside memory for every variable and function declaration it finds, and only then a **code execution phase**, where your code actually runs line by line. **Hoisting** is the name for the effect of that first phase — you can reference a variable or function before the line that defines it, because memory for it was already reserved before execution ever began.

You'll often see hoisting summarized as "JavaScript moves declarations to the top of the file." That's a handy shorthand for predicting behavior, but nothing physically moves — the code stays exactly where you wrote it. What actually happens is memory allocated ahead of time, and *what* gets stored in that memory differs depending on how the thing was declared — which is why hoisting doesn't behave identically for every kind of declaration, and is one of the most common sources of confusing bugs for JavaScript beginners.

## Function declarations are fully hoisted

During the memory creation phase, a function declared with the `function` keyword has its **entire body** copied into memory immediately — not just its name — so it's fully callable before the line where it's written:

```js
sayHello(); // 'Hello!' — works fine

function sayHello() {
  console.log('Hello!');
}
```

### Seeing it for yourself

Most browsers let you pause a script before any of it runs — a breakpoint on the very first line — and inspect the current scope right there in the debugger. Doing that here shows `sayHello` already sitting in memory as a full, callable function, before that line of code has actually executed.

## `var` is hoisted, but only the declaration

A variable declared with `var` gets memory reserved during the same memory creation phase — but instead of a value, the engine fills it with the placeholder `undefined` until the line that assigns it actually runs:

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

Only *function declarations* get their whole body copied into memory upfront. A function assigned to a `var`, `let`, or `const` — including every arrow function — is just a variable as far as the memory creation phase is concerned, and is hoisted the same way that variable is. The function itself isn't usable until its assignment line actually runs:

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

## `undefined` vs. "not defined": two different problems

Hoisting produces a few error-shaped results that are easy to conflate, but they mean different things:

- **`undefined`** means the identifier *was* declared somewhere in scope — memory was reserved for it during the creation phase — but the line that assigns it a real value hasn't run yet.
- **`ReferenceError: x is not defined`** means there's no declaration for `x` anywhere in an accessible scope, full stop — no memory was ever reserved for it, hoisting or otherwise.
- **`ReferenceError: Cannot access 'x' before initialization`** is the TDZ case from `let`/`const` above — a third, distinct message for a variable that *was* declared, just not yet reachable.

```js
console.log(x); // undefined — x is declared below, just not assigned yet
var x = 7;
```

```js
console.log(y); // ReferenceError: y is not defined — y is never declared anywhere
```

These look similar at a glance, but the first is hoisting behaving completely normally; the second means a declaration is missing entirely — often a typo.

## Why this matters

- Relying on hoisting to call a function before its declaration is fine for `function` declarations — it's a normal, documented part of the language.
- Relying on it for `var` variables is a common source of bugs: code appears to work while actually reading `undefined` instead of the intended value.
- `let` and `const`'s TDZ behavior is one of the reasons modern JavaScript style guides recommend them over `var` — mistakes surface immediately as errors instead of silently producing `undefined`.

## Related concepts

- [Function declarations and expressions](./functions.md)
- [Variable Declaration: var, let, and const](../basics/variable-declaration.md)
- [Variables](../basics/variables.md)
- [Constants](../basics/constants.md)
