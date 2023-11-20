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

## Array

- Array is a collection of things. It can hold anything (primary values, objects, functions, another array, Symbols).

## arguments

- `arguments` is an Array like object (not an array), that functions provide for accessing all the parameter values passed during function invocation i.e arguments.
- It has two main functions:
    - accessing variables via [] and index.
    - `arguments.length` property (used to loop over parameters as forEach and other Array methods are not available).
- Common pattern is to convert to array for ease of use.

```javascript
function myFunc() {
    const normalArray = Array.prototype.slice.call(arguments);
    // — or —
    const normalArray2 = [].slice.call(arguments);
    // — or —
    const normalArrayFrom = Array.from(arguments);
}
```

## arguments vs es6 spread

- with es6, spread operator is used instead of arguments as it gives an actual array instead of array like object.
- spread is always be the last item in parameter list.
- spread is allowed exactly once.

```javascript
function myFunc(a, b, ...myargs) {
    // myargs is an array
}
```

## function overloading pattern

```javascript
function greet(firstname, lastname, language) {
        
    language = language || 'en';
    
    if (language === 'en') {
        console.log('Hello ' + firstname + ' ' + lastname);   
    }
    
    if (language === 'es') {
        console.log('Hola ' + firstname + ' ' + lastname);   
    }
    
}

function greetEnglish(firstname, lastname) {
    greet(firstname, lastname, 'en');   
}

function greetSpanish(firstname, lastname) {
    greet(firstname, lastname, 'es');   
}

greetEnglish('John', 'Doe');
greetSpanish('John', 'Doe');
```
