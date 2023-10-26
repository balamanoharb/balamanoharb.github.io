---
layout: "post"
title: "Truthy and Falsy in Javascript"
date: "2023-10-19 21:40:58 +0530"
permalink: truthy-and-falsy-in-javascript
tags: javascript
---

In JavaScript, it is important to understand that, not just the boolean values _true_ and _false_ evaluates to true and false but there are other values which are considered as true and false in certain context.

## Falsy Values

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
if (false) console.log('if check passed')
if (null) console.log('if check passed')
if (undefined) console.log('if check passed')
if (0) console.log('if check passed')
if (NaN) console.log('if check passed')
if ('') console.log('if check passed')
if ("") console.log('if check passed')
if (``) console.log('if check passed')

/* None of above statements will log*/
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

## Boolean Context

- Any boolean conditional that evaluates to true or false
- The simplest example of Boolean context is _if_ condition and _loops_

```javascript
if(<Boolean Conditional>){}

for (control variable; <boolean conditional>; counter) {}
```

## Existence check

- If you need to check for an existence, you can use coercion and boolean context to your advantage.

```javascript
if(myVar) {
    //code block
}
```

- This will be fine for most cases. But if you are expecting 0 or any other falsy values to be in expected valid values, you can simply add them in or condition

```javascript
if(myVar || myVar === 0) {
    //code block
}
```