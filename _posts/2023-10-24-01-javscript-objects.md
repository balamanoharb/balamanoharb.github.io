---
layout: "post"
title: "Objects in JavaScript"
date: "2023-10-24 20:33:02 +0530"
permalink: objects-in-javascript
tags: javascript
---

Object is a collection of name and value pairs. The value can be primitive, another object or a function.

## Creating Objects

1. Using `new`.

```javascript
var data = new Object();
```

2. Using literal.

```javascript
var data = {};
```

## Properties

Properties can be set / mutated / accessed using two different notations.

1. `.` dot operator

```javascript
data.fileName = 'logs.txt'
console.log(data.fileName)
```

- This is preferred over the other for ease of use and readability.

2. `[]` operator

```javascript
data["fileName"] = 'logs.txt'
console.log(data["fileName"])
```

- both does exactly the same thing but [] enables, 

1. property names with special characters
2. dynamic naming

```javascript
var address_details = ["home address", "office address", "home phone"];
address_details.map(prop => [prop, data[prop]]);
```

## Namespace

Objects are used for faking namespace as an Object is self contained.

```
var project = {
    name: "Pokedex",
    version: "0.1",
    run: function () {
        //
    }
}
```

## JSON (JavaScript Object Notation)

- JSON is a subset of JavaScript object.
- JSON is a lightweight format for storing and transporting data.
- All JSON objects are JavaScript objects but not all JS objects are JSON.
- All property names must be enclosed in double quotes.
- JavaScript engine has `JSON.stringify(any_object)` and `JSON.parse(string_value)`
- JSON are used as data formats for communicating.

## Functions are special objects.

- In JavaScript, functions are objects. They vary from conventional objects in few ways:
1. `name` property - stores the name of the function.
2. becomes invokable - `function_name()`.
3. stores the code as value - `function_name` returns the entire code block.

```javascript
function pokeDex() {
    console.log("Initializing the dex...");
}
pokeDex.version = "0.1"; // valid because functions are objects.
```

## statement vs expression

- Statement is a piece of code that does something. All code blocks are statements.

- Expression is a piece of code i.e a statement that evaluates to a value. All expressions are statements. But not all statements are expressions.

> A function is both a statement and an expression.

### function statement

```javascript
function pokeDex() {
    console.log("Initializing the dex...");
}
```

- This does not return anything.
- Only placed in memory as a named function.
- Does not do anything unless executed.

### function expression

```javascript
var pokeDex = function() {
    console.log("Initializing the dex...");
}
```

- an anonymous function (not named) object is returned as value.
- the value is assigned to a variable.
- function behaves as an expression here.
- it can also be passed in function calls like any other object.


## _this_ keyword

- _this_ is set when the execution gets created
- its reference changes depending on lexical and execution context
- at global level it is pointing to window object.
- inside a function defined as an expression for a prop in object, it points to the object itself.
- inside a nested function definition inside objects, it points to global object window, this is considered a bug by many. To mitigate, a pattern relying scope chain is used by setting a variable `self = this` at top level.

```javascript
var data = {
    value: "value 1,
    update: function () {
        let self = this;
        console.log(`previous value: ${this.value}`)
        function update() {
            self.value = 'value set in nested function';
            console.log(`updated value: ${self.value}`)
        }
        update();
    }
}
data.update();
```

- this example contains un n