---
layout: "post"
title: "Arrow functions in JavaScript"
date: "2023-11-10 19:30:57 +0530"
permalink: javascript-arrow-functions
tags: javascript
---

## Why arrow functions

- It is easy and shorter to write.
- In JavaScript, everytime a new execution context is created, a reference to `this` is set during the creation. Since calling a function creates a new execution context, how the value of `this` keyword is hard to deduce and debug at run time. Arrow functions solve this problem by not setting a value to `this`. As a result, usage of `this` references to it's outer lexical scope like any other variable.

```javascript
// Regular function
function add(a, b) {
  return a + b;
}

// Arrow function without parentheses
const add = a => a + b;

// Arrow function with parentheses (when there is more than one parameter, parenthesis is needed)
const add = (a, b) => a + b;


// Arrow function with curly braces
// explicit return statement needed when not a one liner
const add = (a, b) => {
  return a + b;
}

// Arrow function returning an object directly - paranethesis needed when returning object in single line.
const getVal = _ => ({ value: 100})
```

## Limitations

- One limitation with arrow function is that it can't be used inside objects like regular functions because using `this` will be pointing to global context.

```javascript
const state = {
    status: "approved",
    getStatus: () => this.status //this will be point to global object here.
}
```

- In constructors also `this` object will be accessible only inside constructor. But adding arrow functions to `this` object will create a copy of the function to every instance created using the constructor, so arrow functions are generally not used in Constructors.

```javascript
class Test {
    constructor(score) {
        this.score = score;
        this.getScore = () => this.score;
    }
}
```