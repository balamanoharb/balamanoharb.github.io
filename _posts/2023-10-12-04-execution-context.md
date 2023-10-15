---
layout: post
title: "Execution context"
date: "2023-10-12 20:49:15 +0530"
permalink: how-javascript-runs-code
tags: javascript
---

JavaScript is a dynamically typed, synchronous, single threaded, interpreted language i.e:

- dynamically typed: type of the variable is not needed. It is dynamically determined based on value.
- synchronous: uses only one thread to execute all operations in succession
- single threaded: one command at a time
- interpreted: code is run in single step without compiling it to byte code like c, c++.

JavaScript is defined by ECMAScript standard (ecma-262). ECMAScript is defined by the TC39 committee. JavaScript engines implement the standard and make it feasible to run javascript code. All javascript engines use Just In Time (JIT) compilation to compile/interpret code on the fly.

When JS engine runs code, it creates a wrapper/ environment for the currently running code called execution context. It happens in two phases:

1. Memory Allocation/ Creation phase:
    - Variables declared using 'var' are stored  and initialized with the default value 'undefined'.
    - Variables declared using 'let' and 'const' are stored. These variables are marked as un-initialized not containing any value. Technically they are said to be in *temporal dead zone*, till the code gets executed and the assignment happens.
    - function definitions are stored and initialized with the code snippet of the function.
2. Code Execution phase: Parse and run the code line by line. Each execution context maintains it's own environment, containting:
    - this variable
    - reference to outer lexical environment: Physical location of code block in file
    - memory lookup table specific to the current execution context or simply call stack.

![Execution Context](/assets/images/execution-context.png)

When the JavaScript engine starts running code, it creates the global context, this is kept at bottom of call stack. Whenever a function invocation is encountered, it creates new execution context and pushes it to the execution call stack.