---
id: functions/call-apply-bind
title: call, apply, and bind
type: functions
description: Control what `this` refers to inside a function using the built-in call, apply, and bind methods every function inherits.
status: draft
tags:
  - javascript
  - functions
  - this
  - fundamentals
---

# call, apply, and bind

Because [functions are objects](../objects/functions-are-objects.md), every function comes with three built-in methods — `call`, `apply`, and `bind` — for controlling what [`this`](./this-keyword.md) refers to when the function runs.

## Why `this` needs controlling

A method knows its `this` only while it's still attached to the object it was called on. Pull it off into a plain variable and that connection is lost:

```js
const person = {
  name: 'Alice',
  greet() {
    console.log(`Hello, I'm ${this.name}`);
  }
};

person.greet(); // Hello, I'm Alice

const greetFn = person.greet;
greetFn(); // Hello, I'm undefined — `this` no longer refers to `person`
```

`call`, `apply`, and `bind` all exist to fix this: they let you say explicitly which object `this` should point to.

## call()

`call(thisArg, arg1, arg2, ...)` invokes the function immediately, with `this` set to `thisArg` and any remaining arguments passed in one by one:

```js
greetFn.call(person); // Hello, I'm Alice

function greetWithGreeting(greeting) {
  console.log(`${greeting}, I'm ${this.name}`);
}

greetWithGreeting.call(person, 'Hey'); // Hey, I'm Alice
```

## apply()

`apply(thisArg, argsArray)` does exactly what `call` does, except the extra arguments are passed as a single array instead of one at a time:

```js
greetWithGreeting.apply(person, ['Hey']); // Hey, I'm Alice
```

`apply` is handy whenever the arguments already live in an array — a classic pre-spread-operator example is finding the largest number in an array:

```js
const numbers = [3, 7, 2, 9];
Math.max.apply(null, numbers); // 9

// Modern equivalent using the spread operator:
Math.max(...numbers); // 9
```

## bind()

`call` and `apply` both invoke the function right away. `bind(thisArg, ...)` does not — it **returns a new function** with `this` permanently locked to `thisArg`, ready to be called later:

```js
const boundGreet = greetFn.bind(person);

boundGreet(); // Hello, I'm Alice — this always refers to `person`, no matter how boundGreet is called
```

This matters whenever a function is handed off to run later, since the caller decides `this` for a plain function call — and that caller usually isn't the object you meant:

```js
class Timer {
  constructor() {
    this.seconds = 0;
  }

  start() {
    // Without bind, `this` inside tick() would be undefined —
    // setTimeout calls tick() as a plain function, not as timer.tick()
    setTimeout(this.tick.bind(this), 1000);
  }

  tick() {
    this.seconds++;
    console.log(this.seconds);
  }
}
```

## Comparing the three

| Method  | Runs immediately? | Extra arguments               | Returns                              |
| ------- | ------------------ | ------------------------------ | ------------------------------------- |
| `call`  | Yes                 | passed individually             | the function's own return value       |
| `apply` | Yes                 | passed as an array              | the function's own return value       |
| `bind`  | No                  | passed individually (optional)  | a new function, permanently bound     |

## Related concepts

- [The this Keyword](./this-keyword.md)
- [Changing the Value of this](./changing-this.md)
- [Functions are Objects](../objects/functions-are-objects.md)
- [Constructor Functions](../objects/constructor-functions.md)
- [Function declarations and expressions](./functions.md)
