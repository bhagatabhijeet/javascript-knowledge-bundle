---
id: functions/function-types
title: Types of functions
type: functions
description: The different ways to define and categorize functions in JavaScript, from declarations to higher-order and async functions.
status: draft
tags:
  - javascript
  - functions
  - types
---

# Types of functions

JavaScript functions can be categorized by how they are defined and how they are used.

## Named vs anonymous functions

```js
function greet() {}          // named
const greet2 = function () {} // anonymous, assigned to a variable
const greet3 = () => {}       // arrow functions are always anonymous unless assigned
```

## Getter and setter functions

Getters and setters allow you to access and mutate object properties through methods while retaining property syntax:

```js
const person = {
  firstName: 'John',
  lastName: 'Smith',
  get fullName() {
    return `${this.firstName} ${this.lastName}`;
  },
  set fullName(value) {
    const parts = value.split(' ');
    this.firstName = parts[0];
    this.lastName = parts[1];
  }
};

person.fullName = 'Alice Johnson';
console.log(person.fullName); // Alice Johnson
```

## Factory functions vs Constructor functions

- **Factory function**: A function that returns a new object:
  ```js
  function createCircle(radius) {
    return {
      radius,
      draw() { console.log('draw'); }
    };
  }
  ```
- **Constructor function**: Invoked with the `new` operator:
  ```js
  function Circle(radius) {
    this.radius = radius;
    this.draw = function() { console.log('draw'); };
  }
  const circle = new Circle(1);
  ```

## Related concepts

- [Function declarations and expressions](./functions.md)
- [Objects](../objects/objects.md)
- [Variables](../basics/variables.md)
