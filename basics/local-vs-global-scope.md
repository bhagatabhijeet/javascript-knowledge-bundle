---
id: basics/local-vs-global-scope
title: Local vs Global Scope
type: js-basics
description: Understand what makes a variable globally visible versus local to a single function, and what happens when the two share a name.
status: draft
tags:
  - javascript
  - basics
  - scope
  - fundamentals
---

# Local vs Global Scope

**Scope** determines where in your code a variable can be seen and used. Before getting into the block-level detail of [`var`, `let`, and `const`](./variable-declaration.md), it helps to see the bigger picture: a variable is either **global** — visible everywhere — or **local** to the function it was declared in.

## Global scope

A variable declared outside of every function lives in the **global scope**. It's visible everywhere in the program, including inside any function:

```js
let color = 'red';

function printColor() {
  console.log(color); // accessible here — color is global
}

printColor(); // red
```

## Local (function) scope

A variable declared inside a function is **local** to it — it only exists while that function is running, and is completely invisible outside it:

```js
function printColor() {
  let color = 'blue';
  console.log(color);
}

printColor();       // blue
console.log(color); // ReferenceError: color is not defined
```

Each call to `printColor` gets its own fresh `color` — local variables don't persist or share state between calls, and they don't leak out into the surrounding code.

## Shadowing: a local variable can hide a global one

If a local variable has the *same name* as a global one, the local one wins inside that function — it **shadows** the global, without changing it:

```js
let color = 'red';

function printColor() {
  let color = 'blue'; // shadows the global `color` for the rest of this function
  console.log(color); // blue
}

printColor();
console.log(color); // red — the global variable was never touched
```

Inside `printColor`, every reference to `color` means the local one; there's no way to reach the shadowed global from inside that function once it's been shadowed.

## A nested function can see its outer function's locals

Scope nests: a function defined inside another function can read that outer function's local variables, in addition to the global scope:

```js
function outer() {
  let message = 'Hello';

  function inner() {
    console.log(message); // accessible — inner can see outer's local variables
  }

  inner(); // Hello
}
```

This only works one direction — `outer` cannot see any variables declared inside `inner`.

## Why minimize global variables

Every global variable is visible to, and can be overwritten by, *any* other code running in the same program — including third-party scripts on the same page. (This is exactly the risk [top-level `var` creates by attaching itself to `window`](./variable-declaration.md).) The fewer globals a program has, the fewer places two unrelated pieces of code can accidentally collide over the same name — which is why the general rule is to declare variables as locally as possible, and reach for the global scope only when something genuinely needs to be shared everywhere.

## Related concepts

- [Variable Declaration: var, let, and const](./variable-declaration.md)
- [Function declarations and expressions](../functions/functions.md)
- [Hoisting](../functions/hoisting.md)
