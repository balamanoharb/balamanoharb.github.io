---
layout: post
title: "Execution context"
date: "2023-10-12 20:49:15 +0530"
permalink: execution-context-javascript
tags: javascript
---

JavaScript is a dynamically typed, synchronous, single threaded, interpreted language. It is defined by ECMAScript standard (ecma-262). ECMAScript is defined by the TC39 committee. JavaScript engines implement the standard and make it feasible to run javascript code. All javascript engines use Just In Time (JIT) compilation to compile/interpret code on the fly.

When JS engine runs code, it creates a wrapper/ environment for the currently running code called execution context. It happens in two phases:

1. Memory Allocation/ Creation phase:
    - Variables using 'var' are declared and initialized with the default value 'undefined'.
    - Variables using 'let' and 'const' are declared. These variables are marked as un-initialized not containing any value. Technically they are said to be in *temporal dead zone*, till the code gets executed and the assignment happens.
    - function definitions are stored and initialized with the code snippet of the function.
2. Code Execution phase: Parse and run the code line by line. Each execution context maintains it's own environment, containting:
    - this variable
    - reference to outer lexical environment: Physical location of code block in file
    - memory lookup table specific to the current execution context or simply call stack.

![Execution Context](/assets/images/execution-context.png)

When the JavaScript engine starts running code, it creates the global context. This is kept at bottom of call stack.
Whenever a function invocation is encountered, it creates new execution context and pushes it to the execution call stack.

## Hoisting

In the execution context's creation phase, all variables are declared first. This is called _hoisting_. The assignment happens when the interpreter executes the line.

## Scoping

A variable is either function scoped or block scoped based on how they are declared. _var_, _let_ and _const_ are the key words used for declraing variables.

### var

variables declared using _'var'_ are function scoped i.e defining a new function resets the scope.

```javascript
console.log(myVar);
var myVar = "global variable";
console.log(myVar);
function printVar() {
    console.log(myVar);
    var myVar = "function variable";
    console.log(myVar);
}
printVar();
console.log(myVar)
/*output
undefined // indicating it is hoisted
"global variable"
undefined // indicating myVar inside the function is different and hoisted
"function variable"
"global variable"
*/
```

> var is no longer used in production scenario as function scope is harder to use.
> var allows re-declaring same variable.
> var enables hoisting making it harder to debug.
> At top level variables declared using var are placed in global object

### let, const

let and const are block scoped i.e every time a new block _{ }_ is encountered, the scope is reset.

```javascript
// temporal deadzone error
console.log(myVal); //Uncaught ReferenceError: Cannot access 'myVal' before initialization
let myVal ;
```

unlike _var_, let can't be re-declared in same scope.

```javascript
let myVal = 'test';
let myVal = 100; //Uncaught SyntaxError: Identifier 'myVal' has already been declared
```

```javascript
let myVal = 'global scope 1';
console.log(myVal)
{
    let myVal = 'block scope level 1';
    console.log(myVal);
    {
        let myVal = 'block scope level 2;
        console.log(myVal);
    }
}
console.log(myVal);
```

only difference between _let_ and _const_ is that, variables defined using const can't be re-assigned. This means const is always defined and can't be declared. If the const value is a non primitive type, it can be modified without re-assigning.

```javascript
const val; //Uncaught SyntaxError: Missing initializer in const declaration
const myVal = 100; //right way to use const
myVal = 200; //Uncaught TypeError: Assignment to constant variable.
const list = ['apple']
list.push('organ') //modifying is allowed.
```

> In current production scenarios, only let and const are used.

## Scope Chain:

Whenever a variable is encountered, javascript first checks if the variable is defined in the currently running execution context. If it is not found, it follows the reference to its outer lexical environment. If the variable is not found there, it again follows the reference to the outer lexical environment of the current execution context. If the variable is found at any point, the lookup is stopped and the value found is returned. If it is not found, it goes up the chain of references till it reaches the global context. Only when it is not found, it throws _"Uncaught ReferenceError: variable name is not defined"_.


## Definitions

- _dynamically typed_: type of the variable is dynamically determined based on value.
- _synchronous_: uses only one thread to execute all operations in succession
- _single threaded_: runs one command at a time
- _interpreted_: code is run in single step without compiling it to byte code like c, c++.
- _declaration_ : A variable is named and known to exist but value is not yet assigned.
- _assignemnt_: A variable is assigned a value or an expression that executes to a value. `x = 10;`
- _definition_ : declaration + assignment in a one statement = definition. `var x = 10;`