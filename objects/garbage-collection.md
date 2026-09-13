---
id: objects/garbage-collection
title: Garbage Collection
type: objects
description: JavaScript automatically reclaims memory used by objects that are no longer reachable.
status: draft
tags:
  - javascript
  - objects
  - fundamentals
  - memory
---

# Garbage Collection

In lower-level languages like C or C++, creating an object means manually **allocating** memory for it — and once you're done with it, you have to manually **deallocate** that memory yourself. Forget the second step, and the memory leaks.

JavaScript doesn't ask you to do either of these things:

```js
let circle = {};
console.log(circle); // {}
```

The moment `circle` is initialized, the JavaScript engine automatically allocates memory for it. You go on to use the object, and when you're done with it, you don't have to deallocate anything yourself.

## The garbage collector's job

Instead, the JavaScript engine has a **garbage collector**: a background process whose job is to find variables and constants that are no longer used, and free the memory that was allocated to them earlier.

```js
let circle = { radius: 1 };
circle = null; // nothing references the original { radius: 1 } object anymore
```

Once nothing points to the `{ radius: 1 }` object, it becomes eligible for garbage collection, and the engine frees its memory at some later point.

As a JavaScript developer, you don't manage any of this yourself. Memory allocation and deallocation happen automatically behind the scenes, and you have no control over it — you can't tell the garbage collector when to run, or which variables to remove from memory. Based on its own internal algorithms, it periodically figures out which variables are no longer reachable and deallocates their memory for you.

## Mark-and-sweep

One such algorithm, used by modern engines like V8, is **mark-and-sweep**: starting from a set of root references (global variables, currently executing function calls), the collector marks every object it can still reach, then sweeps away — frees — everything left unmarked.

## Why you rarely manage this yourself

Unlike languages with manual memory management, JavaScript developers do not need to explicitly free objects. Setting a variable to `null` can help release a reference early in long-lived programs, but it is rarely necessary in typical application code.

## Related concepts

- [Value vs Reference Types](./value-vs-reference-types.md)
