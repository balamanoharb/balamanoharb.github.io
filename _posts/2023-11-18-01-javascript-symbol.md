---
layout: "post"
title: "Symbol in JavaScript"
date: "2023-11-18 15:20:45 +0530"
permalink: javascript-symbol
tags: javascript
---

## Why arrow functions

- Symbol is a primitive type in Javascript.
- Symbol constructor is used for creating symbol object.
- Symbols are used for creating unique identifiers i.e every symbol is unique.
- Apart from creating unique identifiers, they can be given a name or description at time of creation.

```javascript
let id1 = Symbol();
let id2 = Symbol();
id1 === id2 //false

let val1 = Symbol("COLOR");
let val2 = Symbol("COLOR");
val1 === val2; //false
```

### Use Cases

- Since Symbol is a primitive type, they can be used to create properties in objects. When a symbol is used as a property name, name collision inside the same object can be avoided. This is particularly useful in libraries where you want to prevent property names to be not overridden.

```javascript
const configName= Symbol("configName");
class Config {
    [configName] = 'UserSettings';
    constructor(user) {
        // initi user specific settings
    }

    getConfigName() {
        return this[configName];
    }
}

let config = new Config('<userObject>');
config.getConfigName()
```

- Symbol has many useful methods. `for` are used for creating global Symbols with a string value. `keyfor` is used to fetch the value stored in a global symbol (counter part of `for` method). 

```javascript

const RED = Symbol.for("RED");
const myColor = Symbol.for("RED");

RED === myColor //true - for method adds symbols to global space maintaining uniquenes across

Symbol.keyFor(myColor) //returns RED
```

### Wellknown Symbols

- Symbols that are added to JS engine by default.
-  `Symbol.iterator` is a well known used for enabling an object to become iteratable.
- `for..of` expects any object being iterated over to define a method using `Symbol.iterator` as property name and the return value to be an object having `{ next: () => { value: , done: <boolean value> }`

```javascript
let iteratableObject = {
    key1: 100,
    key2: 200,
    key3: 400,
    backupKey: 1000,
    [Symbol.iterator]: function() {
        const iterableKeys = ['key1', 'key2', 'key3'];
        let i = 0;
        return {
            next: () => {
                return {
                    value: this[iterableKeys[i++]],
                    done: i-1 == iterableKeys.length
                }
            }
        }
    }
}

for (let val of iteratableObject) {
    console.log(val);
}
```

- another example of making an array iterate in reverse

```javascript
const reverse = arr => ({
  [Symbol.iterator]() {
    let i = arr.length;
    return {
      next: () => ({
        value: arr[--i],
        done: i < 0
      })
    }
  }
})

let nums = [1, 2, 3, 4, 5]

for (let num of reverse(nums)) {
  // ...
}

console.log(nums)               // [1, 2, 3, 4, 5]
```
