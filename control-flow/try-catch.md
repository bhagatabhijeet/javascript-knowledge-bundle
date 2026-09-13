---
id: control-flow/try-catch
title: Try, Catch, and Throw
type: control-flow
description: Report invalid situations with throw, and handle them gracefully with try/catch instead of letting the program crash.
status: draft
tags:
  - javascript
  - control-flow
  - error-handling
  - fundamentals
---

# Try, Catch, and Throw

## The problem: bad input crashes the program

A function that assumes its input is always well-formed breaks the moment that assumption is wrong. Take a [setter](../functions/getters-and-setters.md) that expects a string to split into a first and last name:

```js
set fullName(value) {
  const parts = value.split(' ');
  this.firstName = parts[0];
  this.lastName = parts[1];
}
```

Pass it a boolean, and it crashes — booleans don't have a `split` method:

```js
person.fullName = true; // Uncaught TypeError: value.split is not a function
```

Pass `null` or `undefined`, and it crashes too, with a different message (`Cannot read properties of null`). Either way, the whole program stops.

## Defensive programming: validate first

The fix starts at the top of the function: check that the input actually looks the way the code assumes it does, *before* using it:

```js
set fullName(value) {
  if (typeof value !== 'string') {
    return; // silently do nothing
  }

  const parts = value.split(' ');
  this.firstName = parts[0];
  this.lastName = parts[1];
}
```

This stops the crash, but silently returning has its own problem: the caller has no idea anything went wrong — the assignment just quietly did nothing. Sometimes that's fine; often you want to actually report the problem.

## `throw`: reporting a problem properly

Instead of returning quietly, **throw** an error object to signal that something exceptional happened:

```js
set fullName(value) {
  if (typeof value !== 'string') {
    throw new Error('Value is not a string.');
  }
  // ...
}
```

`Error` is a built-in constructor function — `new Error('...')` creates a plain object with a `message` property, nothing more. It only becomes an **exception** the moment it's `throw`n; up until then it's just an ordinary object.

Throwing immediately stops the function — any code written after the `throw` statement never runs. Control jumps straight out, looking for somewhere to catch it.

## `try`/`catch`: handling the exception

An uncaught exception crashes the program the same way the original `TypeError` did. To handle it, wrap the risky code in a **`try`** block, followed by a **`catch`** block that receives whatever was thrown:

```js
try {
  person.fullName = true;
} catch (e) {
  console.error(e); // only visible to developers, in the console
}
```

The identifier in `catch (e)` — call it `e`, `error`, whatever reads well — holds the exact value that was thrown, typically the `Error` object. Inside `catch`, you can log it, show the user a message, or otherwise recover instead of letting the whole program stop.

## Putting it together

```js
const person = {
  firstName: 'Mosh',
  lastName: 'Hamedani',
  set fullName(value) {
    if (typeof value !== 'string') {
      throw new Error('Value is not a string.');
    }

    const parts = value.split(' ');
    if (parts.length !== 2) {
      throw new Error('Enter a first and last name.');
    }

    this.firstName = parts[0];
    this.lastName = parts[1];
  }
};

try {
  person.fullName = '';
} catch (e) {
  console.error(e); // Error: Enter a first and last name.
}
```

The setter can throw for more than one reason — a non-string value, or a string that isn't in the "first last" shape — and a single `catch` handles whichever one actually happens.

## Related concepts

- [Getters and Setters](../functions/getters-and-setters.md)
- [If...else](./if-else.md)
- [Function declarations and expressions](../functions/functions.md)
