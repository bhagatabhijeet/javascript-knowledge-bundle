---
id: functions/rest-operator
title: Rest Operator
type: functions
description: Collect any number of remaining function arguments into a real array using the rest operator (...), the modern replacement for the arguments object.
status: draft
tags:
  - javascript
  - functions
  - rest-operator
  - es6
  - fundamentals
---

# Rest Operator

The **rest operator** (`...`) collects every argument a function was called with — however many there are — into a real, ordinary array:

```js
function sum(...args) {
  return args.reduce((a, b) => a + b, 0);
}

console.log(sum(1, 2, 3, 4)); // 10
```

## Why prefer it over the `arguments` object

[`arguments`](./functions.md) does something similar, but the rest operator improves on it in a few concrete ways:

- `args` is a genuine `Array` — `map`, `filter`, `reduce`, and every other array method work directly on it. `arguments` is only array-*like*, and has none of them.
- Arrow functions don't have their own `arguments` object at all — inside an arrow function, `arguments` refers to whatever enclosing regular function's `arguments` happens to be in scope, which is rarely what you want. The rest operator works in arrow functions exactly as it does anywhere else.
- The name is yours to choose (`args`, `numbers`, `items`, ...) rather than the fixed, magic name `arguments`.

## Combining rest with named parameters

Rest can follow one or more regular, named parameters — it just collects whatever's left over after those are filled:

```js
function greet(greeting, ...names) {
  return names.map(name => `${greeting}, ${name}!`);
}

greet('Hi', 'Alice', 'Bob'); // ['Hi, Alice!', 'Hi, Bob!']
```

## Rest must be the last parameter

Because it scoops up everything remaining, a rest parameter has to come last — anything declared after it would never receive a value:

```js
function invalid(...args, last) {} // SyntaxError: Rest parameter must be last formal parameter
```

## Rest vs. spread: opposite directions, same `...`

It's easy to conflate these since they share syntax, but they do opposite jobs:

- **Rest** (in a function's parameter list) *collects* multiple arguments **into** an array.
- [**Spread**](../arrays/spread-operator.md) (in a function call, or inside an array/object literal) *expands* an array **out into** multiple values.

```js
function sum(...args) {         // rest: gathers the call's arguments into args
  return args.reduce((a, b) => a + b, 0);
}

const numbers = [1, 2, 3];
sum(...numbers); // spread: expands numbers back out into individual arguments — 6
```

## Related concepts

- [Function declarations and expressions](./functions.md)
- [The Spread Operator](../arrays/spread-operator.md)
- [Arrow Functions](./arrow-functions.md)
