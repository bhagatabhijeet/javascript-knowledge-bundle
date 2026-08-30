---
id: javascript/fundamentals/introduction
title: JavaScript introduction
type: Concept
description: An introduction to JavaScript, why it matters, and how the browser and runtime execute code.
status: stable
trust: human-reviewed
stale: false
tags:
  - javascript
  - fundamentals
  - introduction
---

# JavaScript introduction

JavaScript is one of the most important programming languages in modern software development. It is the language that makes web pages interactive, powers front-end frameworks, and is also used on the server with Node.js.

In simple terms, JavaScript helps you tell the browser and other runtimes what to do when users click buttons, load pages, fetch data, or update content in real time.

## Why JavaScript is important

JavaScript is valuable because it is:

- widely used in web development
- supported by every modern browser
- flexible enough for small scripts and large applications
- part of the full-stack ecosystem through Node.js
- a foundation for frameworks like React, Vue, and Angular

## What JavaScript does

JavaScript can:

- update page content dynamically
- validate forms before submitting data
- react to clicks, keyboard input, and timers
- fetch data from APIs and display it in the UI
- run logic for dashboards, games, editors, and browser tools

## How JavaScript runs

JavaScript runs inside a runtime environment such as a browser or Node.js. The runtime executes code using a call stack, memory, and an event loop for asynchronous work.

This means JavaScript can handle many actions without blocking the whole program. For example, a request can run in the background while the user continues interacting with the page.

## A first example

```js
console.log('Hello, JavaScript!')

const name = 'Ada'
const message = `Welcome, ${name}!`

console.log(message)
```

This is a basic example, but it shows the heart of JavaScript: values, variables, and output.

## Core mental model

When learning JavaScript, it helps to think in terms of:

- values and variables
- functions and logic
- objects and arrays
- events and user interaction
- asynchronous behavior with promises and async/await

These ideas build on each other. The more you practice, the easier it becomes to read and write real programs.

## In one sentence

JavaScript is the language that brings websites and applications to life by turning static pages into interactive experiences.

## Related concepts

- [Variables and declarations](./variables.md)
- [Function declarations and expressions](./functions.md)
- [Objects and object literal patterns](./objects.md)
