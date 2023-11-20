---
layout: "post"
title: "Functional programming in JavaScript"
date: "2023-10-29 14:58:29 +0530"
permalink: functional-programming-in-javascript
tags: javascript
---

- Do everything in terms of functions. Take in an input and give out an output
- Avoid side effects and write only pure functions, i.e take in an input and use only that input to produce an output.

```javascript
// not pure - uses global variable.
var name = "Bala"
function greet() {
    return "Hello!! " + name;
}
greet();
// pure function
function greet(name) {
    return "Hello!! " + name;
}
greet("Bala")
```

- Use higher order function: take function as an input/ produce functions as an output.

```javascript
function makeAdjectifier(adjective) {
    return function (string) {
        return adjective + " " + string;   
    };
}
var coolifier = makeAdjectifier("cool");
coolifier("conference");  => "cool conference"

```

- Don't iterate (Avoid for, while): use map, reduce, filter instead.
- Do not mutate input.
- Use persistent immutable data structures.

## Source

- https://www.youtube.com/watch?v=e-5obm1G_FY
- https://codewords.recurse.com/issues/one/an-introduction-to-functional-programming

