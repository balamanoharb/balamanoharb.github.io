---
layout: "post"
title: "Finding types in JavaScript"
date: "2023-10-29 15:32:11 +0530"
permalink: find-types-in-javascript
tags: javascript
---


- use the typeof keyword.
- The typeof operator maps an operand to one of eight possible values:
    - "string"
    - "number" // NaN also returns number
    - "object" // Array and null also returns object
    - "function"
    - "undefined"
    - "boolean"
    - "symbol"
    - "bigint"
- The instanceof method tests if the provided function's prototype is in the object's prototype chain.
- Short hack to get Array also as a type

```javascript
Object.prototype.toString.call(obj).slice(8, -1).toLowerCase()
```