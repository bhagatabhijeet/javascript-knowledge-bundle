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

JavaScript manages memory automatically. When you create an object, the engine allocates memory for it; when that object is no longer reachable from anywhere in your program, the engine's **garbage collector** reclaims that memory.

```js
let circle = { radius: 1 };
circle = null; // the original object is no longer referenced by anything
```

Once nothing points to the `{ radius: 1 }` object, it becomes eligible for garbage collection, and the JavaScript engine frees its memory at some later point.

## Mark-and-sweep

Modern engines use a **mark-and-sweep** algorithm: starting from a set of root references (global variables, currently executing function calls), the collector marks every object it can reach, then sweeps away — frees — everything left unmarked.

## Why you rarely manage this yourself

Unlike languages with manual memory management, JavaScript developers do not need to explicitly free objects. Setting a variable to `null` can help release a reference early in long-lived programs, but it is rarely necessary in typical application code.

## Related concepts

- [Value vs Reference Types](./value-vs-reference-types.md)
