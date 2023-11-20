---
layout: "post"
title: "Exploring a library structure"
date: "2023-10-29 19:17:24 +0530"
permalink: exploring-simple-library
tags: javascript
---

- dummy library based on jQuery

```javascript
(function(global) {

    // new object
    var Lib = function (...args) {
        return new Lib.init(args);
    }

    // init Library variables
    var x;
    var y;


    // common functions
    Lib.prototype = {
        // function description
        function1: function () {

            // allows chaining like jQuery
            return this;
        },

        // function description
        function2: function () {

            // allows chaining like jQuery
            return this;
        }
    }

    Lib.init = function(args) {
        
        var self = this;
        self.arg1 = args[0];
        // assign object properties
    }
    
    // trick borrowed from jQuery so we don't have to use the 'new' keyword
    Lib.init.prototype = Lib.prototype;
    
    // shorthand alias 'L$'
    global.Lib = global.L$ = Lib;

})(window)
```