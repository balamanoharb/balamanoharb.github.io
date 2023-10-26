---
layout: "post"
title: "Operators, Precedence, Associativity and Coercion"
date: "2023-10-18 20:47:51 +0530"
permalink: operators-precedence-associativity-coercion-in-javascript
tags: javascript
---

## Operators

Consider operators to be a function accepting arguments that is written in infix notation.

## Precedence

When different operators are present in an operation, precedence determines the order in which operations are performed.

## Associativity

When two or more operators of same precedence appears, associativity determines the direction of evaluating the operation.

> Precedence > Associativity

In JavaScript, precedence comes before associativity.

Refer: [Operator Precedence and Associativity](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Operator_Precedence){:target="_blank"}{:rel="noopener noreferrer"}

## Coercion

When the data type of variable is converted from one type to another, it is called Coercion. There are only 3 types of conversion that can happen in JavaScript (in no particular order):

1. to string
2. to boolean
3. to number

> When evaluating any operation, all of the above concepts (precedence, associativity and coercion) are in play.

### Explicit Coercion

When explicitly conversion function is called.

#### String Conversion

```javascript
String(123)                   // '123'
String(-12.3)                 // '-12.3'
String(null)                  // 'null'
String(undefined)             // 'undefined'
String(true)                  // 'true'
String(false)                 // 'false'
```

- String to Symbol implicit conversion follows its own rules. Refer: https://leanpub.com/understandinges6/read/#leanpub-auto-symbol-coercion

#### Boolean Conversion

```javascript
// Returns true / false based on truthy and falsy values.
// Except falsy values, all other values will return true
Boolean('')           // false
Boolean(0)            // false     
Boolean(-0)           // false
Boolean(NaN)          // false
Boolean(null)         // false
Boolean(undefined)    // false
Boolean(false)        // false

// Even these falsy looking values
Boolean({})             // true
Boolean([])             // true
Boolean(Symbol())       // true
!!Symbol()              // true
Boolean(function() {})  // true
```

- in production scenarios, `!!<expression>` is often used as shortcut to convert any value to boolean.


#### Numeric conversion

```javascript
Number(null)                   // 0
Number(undefined)              // NaN
Number(true)                   // 1
Number(false)                  // 0
Number(" 12 ")                 // 12
Number("-12.34")               // -12.34
Number("\n")                   // 0
Number(" 12s ")                // NaN
Number(123)                    // 123
```

- When unable to convert, it returns a special value `NaN`.

### Implicit Coercion

When an operation with variables of different data types are encountered, automatically one data type is converted to another by the JS engine based on its rules. This is implicit coercion.

```javascript
'1' + 1 //11
1 < 2 < 3
// true but the reason it returns true is not how we usually operate
// 1. look up precedence, all operators are of same type. 
// 2. check associativity - left to right in this case
// 3. 1 < 2 => true
// 4. true < 3 => coercion
// 5. Number(true) < 3 => 1 < 3 => true
3 < 2 < 1 // following same logic as above => false < 1 => 0 < 1 => true
```

As you can see, coercion can give surprising results sometimes. The most commonly affected is the equality opeartor '=='.

## Loose equality / Double equals operator (==)

> TL;DR; Don't use '=='. Use '===' instead

Loose equality operator **==** may cause some unexpected errors due to funky implicit coercion that takes place whenever the types of the values involved doesn't match.

To evaluate a simple **x == y** statement, JavaScript follows a complex set of rules refer: [ECMAScript Standard 13.0 - isLooselyEqual(x,y)](https://262.ecma-international.org/13.0/#sec-islooselyequal){:target="_blank"}{:rel="noopener noreferrer"}

### ToNumber in context of "=="

| Value          | Becomes…|
| ---------------|---------| 
| true and false | 1 and 0 |
| string         | Whitespaces from the start and end are removed. If the remaining string is empty, the result is 0.|

- when boolean and numbers are involved. Instead of converting number to Boolean, Booleans are converted to Numbers.
- when a boolean and number are used in "==" operator, the only times when they can become _true_ are these

```javascript
true == 1; // true
1 == true; // true
false == 0; // true
0 == false; // true
```

- Any other variation of number and boolean would always end up as _false_

```javascript
true == 200; // false
1000 == true; //false
true == 123; // false
false == 1; // false
1309 == false; // false
```

- similar to false, null also evaluates to 0 in context of loose equality.

```javascript
null == 0
```

- considering above, you would think, `null < 1` should evaluate to true, but that's not the case. This is because each operator, like "==", has its own set of rules on how to apply coercion.

- string examples

```javascript
"     " == 0 // true
"  1  " == true // true
true = " 1 " // true
123 == "123" // true
123 == "  123  " //true
"123" == 123 //true
"   123  " == 123 //true
```

- when string contains anything other than the number, it will return false

### ToPrimitive in context of "=="

- The simplest case for object coercion to primitive values is converting to **Boolean**. It always coerces to **true** whether it is an array or an Object.
- For coercing an Object to String or a Number, Object.prototype includes two functions called **toString** and **valueOf** . Since it is on the top of protypal inheritance chaing, it will be available to all objects by default.
- To convert an Object, lets say _input_ to a primitive type, these functions _input.toString()_ and _input.valueOf()_ are called in sequence. If any of that function returns a primitive value, then it is returned otherwise it throws error.
- For _String_ conversion _toString_ is called first.
- For _Number_ conversion _valueOf_ is called first.
- In the context of **"=="** operator, no preferred type is assumed, so by default, **valueOf** is called first, followed by **toString**. Most of the native objects when calling the valueOf() method returns the object itself. So the toString() method is used more often.
- Any one can override these two methods and change the default behavior.

```javascript
// to check valueOf is called first
var myNum = 123;
var myObj1 = { valueOf: () => 123, toString: () => "I'm a string" };
var myObj2 = { valueOf: () => [1, 2, 3], toString: () => 123 };
123 == myObj1; // true
123 == myObj2; // true
```

- manipulating these functions, you can arrive at some strange statements. For example this question.
  > Can _(a==1 && a==2 && a==3)_ ever evaluate to true?
  > Answer — Yes.

```javascript
const a = {
  val: 0,
  valueOf: function() {
    return (this.val += 1);
  }
};
console.log(a == 1 && a == 2 && a == 3); // true
```

- Although something like this is possible, in a production level codebase one would never come across code like this.

### Boolean Context vs Equality

- People often confuse "==" with Boolean context. For example,

```javascript
const a = 100;
if (a) {
  console.log("I passed");
}
//I passed

console.log(100 == true); //false
```

- This is because coercion is different for Boolean contexts.
- Boolean contexts are places where a Boolean value is expected. In such cases if the expected value is not Boolean, then it is directly converted to Boolean.
- Some examples of Boolean contexts are

```javascript
if (myTruthyOrFalsyValue) {
}

while (myTruthyOrFalsyValue) {}

for (; myTruthyOrFalsyValue; ) {}
```

- In these places there are no operators involved. So special coercion rules involving operators instead they value is converted to Boolean implicitly.
- This is why truthy and falsy values can be used in those places.

## Strict Equality / Triple Equal Operator (===)

- Triple Equal **===** checks for both the **type** and the **value** instead of doing any coercion.
- It is straight forward and how the equality should have worked in the first place.

```javascript
15 === 15; // true
"hello world" === "hello world"; // true
true === true; // true

true === 1; //false
0 === false; // false
100 === "100"; //false
123 === { valueOf: () => 123, toString: () => "I'm a string" }; //false
```

- "===" simplifies usage. If you are thinking of using "==", look up this <a href="https://dorey.github.io/JavaScript-Equality-Table/" target="_blank" rel="nofollow noopener" title="equality comparison">chart</a>

> Like the equality operator, each operator has a set of rules on how different data types should be coerced. Refer ECMAScript standards for details.

