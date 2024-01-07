---
layout: "post"
title: "Aync programming in JavaScript"
date: "2023-12-16 14:18:30 +0530"
permalink: javascript-async-programming
tags: javascript
---

## Synchronous vs Asynchronous

- Synchronous: Blocking architecture. Only one thing happening at a time. Sequential - one after the other.
- Asynchronous: Non-blocking architecture. A task doesn't need to wait for the task before it to run.

## Asynchronous functions in JS

- setTimeout / setInterval
- reading a File
- triggering http calls

## Callback examples

- setTimeout

```javascript
function printValue() {
    console.log("Invoked after 1000ms");
}

function getValueWithDelay(callback) {
    setTimeout(callback, 1000);
}

getValueWithDelay(printValue)
```

- fs.readFile in nodejs - it uses error first callbacks (a pattern)

```javascript
fs = require("fs")

function readFile(filePath, callback) {
    fs.readFile(filePath, {encoding: 'utf-8'}, function(err, data) {
        callback(data);
    });
}

function printFile(content) {
    console.log(content);
}

readFile("test.txt", printFile);
```

- old way to fetch data

```javascript
function get(url, callback) {
    const request = new XMLHttpRequest();
    request.onload = function(e) {
        if (this.status === 200) {
            callback(this.response);
        }
    }
    request.open('GET', url);
    request.send();
}

function handleResponse(response) {
    // process response here
    console.log(response)
}

get("https://jsonplaceholder.typicode.com/users/1", handleResponse)
```

## Promises

- promises are a syntax sugar for callbacks
- Promise is a class provided by JS engine like Date
- resolve is similar to callbacks. It calls the function passed in then statement with arguments passed in resolve.

- structure of a promise

```javascript
// structure of a promise
//resolveFunction - can be named anything, it's actually callback
new Promise(function(resolveFunction) {
    resolveFunction(resolvedValue)
})
.then(callback);
```

- promise has three states: pending, fulfilled and rejected


```javascript
function getValueWithDelay(delay) {
    return new Promise(function(resolve) {
        setTimeout(function() {
            resolve('random value')
        }, delay)
    })
}

function printValue(returnedValue) {
    console.log(returnedValue);
}

getValueWithDelay(2000)
    .then(printValue);
```

- mostly you'll be dealing with .then part as you'll be consuming prmises rather than write your own.

- readFile

```javascript
function readFile(filename){
  return new Promise(function (fulfill, reject){
    fs.readFile(filename, {encoding: 'utf-8'}, function (err, res){
      if (err) reject(err);
      else fulfill(res);
    });
  });
}

function printFile(content) {
    console.log(content)
}

readFile("test.txt")
    .then(printFile);
```

- promises can be chained as long as the returned value in then is another promise


```javascript
function get(url) {
    // fetch returns a promise
    return fetch(url)
}

function convertToJson(response) {
    // the resolved value from fetch is a response object on which json() function can be called
    // json() function returns a promise again
    return response.json()
}

function handleResponse(response) {
    console.log(response);
}

get("https://jsonplaceholder.typicode.com/users/1")
    .then(convertToJson)
    .then(handleResponse)
```

## Async / Await

- async await is also a syntactic sugar for callbacks
- if a function is returning promise you can use await in front of it.
- if a function is using await inside, it must use async keyword
- await can't be used outside of async function
- much cleaner to use and easier to understand

```javascript
function getValueWithDelay(delay) {
    return new Promise(function(resolve) {
        setTimeout(function() {
            resolve('random value')
        }, delay)
    })
}

async function printValue() {
    // what ever is passed in resolve will be returned
    let value = await getValueWithDelay(2000);
    // what ever is after await will be considered to be part of resolve function.
    // implicit meaning
    // (function (value) { content after await call })(value);
    console.log(value);
}

printValue();
```