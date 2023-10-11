---
title: "Understanding Truthy and Falsy in Javascript"
date: "2019-01-20T15:46:16.386Z"
category: "tech"
tags:
  - javascript
---

## Truthy and Falsy values in JavaScript

In JavaScript, it is important to understand that, not just the boolean values _true_ and _false_ evaluates to true and false but there are other values which are considered as true and false in certain context.

### Falsy Values

- Values that evaluate to _false_ in Boolean context
- There are a total of six falsy values in javascript

1. false
2. 0
3. "" or '' (an empty string)
4. NaN
5. undefined
6. null

- all of these are considered to be false

```javascript
if (false)
if (null)
if (undefined)
if (0)
if (NaN)
if ('')
if ("")
if (``)
if (document.all)
```

### Truthy Values

Values that evaluate to _true_ in Boolean context.

- Everything except falsy values are true
- Even an empty object

```javascript
// true boolean value
if (true)
// any object
if ({})
if ([])
if (42)
if ("foo")
if (new Date())
// any number
if (-42)
if (3.14)
if (-3.14)
if (Infinity)
if (-Infinity)
```

### Boolean Context

- Any boolean conditional that evaluates to true or false
- The simplest example of Boolean context is _if_ condition and _loops_

```javascript
if(<Boolean Conditional>){}

for (control variable; <boolean conditional>; counter) {}
```
