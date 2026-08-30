---
id: fundamentals/arrays
title: Arrays
type: js-basics
description: Create, access, and transform ordered collections with JavaScript arrays and their built-in methods.
status: draft
tags:
  - javascript
  - fundamentals
  - arrays
  - collections
generated: { by: claude/sonnet-5, at: 2026-08-29T00:00:00Z }
sources:
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Array
  - resource: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Indexed_collections
---

# Arrays

An array is an ordered, zero-indexed collection of values. Elements can be any type, including a mix of types.

```js
const fruits = ['apple', 'banana', 'cherry']
fruits[0]        // 'apple'
fruits.length     // 3
```

## Adding and removing elements

```js
fruits.push('date')     // add to the end
fruits.pop()             // remove from the end
fruits.unshift('kiwi')   // add to the start
fruits.shift()           // remove from the start
```

## Slicing and splicing

```js
fruits.slice(1, 3)       // returns a new array, original unchanged
fruits.splice(1, 1, 'x') // mutates the original: removes 1 item at index 1, inserts 'x'
```

## Iterating and transforming

These methods take a callback function and do not mutate the original array (except where noted above):

```js
const numbers = [1, 2, 3, 4]

numbers.map((n) => n * 2)          // [2, 4, 6, 8]
numbers.filter((n) => n % 2 === 0) // [2, 4]
numbers.reduce((sum, n) => sum + n, 0) // 10
numbers.forEach((n) => console.log(n)) // no return value, side effects only
```

## Searching

```js
numbers.includes(3)   // true
numbers.indexOf(3)    // 2
numbers.find((n) => n > 2) // 3, first match
```

## Spreading and combining

```js
const combined = [...numbers, 5, 6]
const copy = [...numbers]
```

## Arrays are objects

`typeof` reports arrays as `'object'`. Use `Array.isArray()` to check for an array specifically.

```js
typeof numbers        // 'object'
Array.isArray(numbers) // true
```

## Related concepts

- [Objects and object literal patterns](./objects.md)
- [Primitive data types](./primitive-types.md)
- [Types of functions](./function-types.md)

This draft was generated from general knowledge of MDN's JavaScript documentation and has not been checked against a live source. It should receive human review before its status is promoted or a `verified` entry is added.
