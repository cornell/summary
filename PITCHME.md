# You don't known JS

---

## 01-up-going

### Chapter 1: Into Programming

#### toFixed() function

```js
    > 301.597.toFixed()
    > "302"

    > 301.597.toFixed(2)
    > "301.60"

    > 301.597.toFixed(1)"
    > 301.6"
```
@[1-2]
@[4-5]
@[6-7]
---
### Chapter 2 : Into Javascript
---
#### Values & types

* string
* number
* boolean
* null and undefined
* object
* symbol (new to ES6)

---

##### typeof

Note:
Examine une valeur et détermine son type:

```js
    var a;
    typeof a;
    > "undefined"

    typeof "coucou"
    > "string"

    typeof 42
    > "number"

    typeof true;
    > "boolean"

    var a = null;
    typeof a;
    > "object"

    var a = undefined;
    > typeof a;
    > "undefined"

    var a = { "key": value };
    > typeof a
    > "object"

    var a = [];
    > typeof a;
    > "object"

    typeof(function() {        
        // code
    });
    > "function"
```
@[1-3]
@[5-6]
@[8-9]
@[11-12]
@[14-16]
@[18-20]
@[22-24]
@[26-28]
@[30-33]
---
#### Objects

```js
    var obj = {
        age: 42,
    };

    > obj.a;
    > 42

    > obj['a'];
    > 42

    var property = 'age';
    > obj[property]
    > 42
```
@[1-3]
@[5-6]
@[8-9]
@[11-13]
---
##### Arrays

un 'array' est un 'object' spécial.

##### Functions

une 'function' est un 'object' spécial.

#### Built-in Type methods

#### Comparing Values

##### Coercion

#### Variables

##### Function Scopes

###### Hoisting
---
#### Strict Mode

```js
    'use strict';
```
---
#### Functions as values

```js
    // fonction expression anonyme
    var foo = function() {
    };

    fonction expression nommée
    var x = function bar(){
    // ..
    };
```
---
##### Immediately Invoked Function Expressions (IIFEs)

```js
    (function IIFE(){
        
    })();
```

Note:
Because an IIFE is just a function, and functions create variable scope, using an IIFE in this fashion is often used to declare variables that won’t affect the surrounding code outside the IIFE:    

```js
    var a = 42;
    (function IIFE(){
        var a = 10;
        console.log( a ); // 10
    })();
    console.log( a ); // 42
```
---
IIFEs can also have return values:

```js
    var x = (function IIFE(){
        return 42;
    })();

    > x; 
    > 42
```

Note:
The 42 value gets returned from the IIFE -named function being executed, and is then assigned to x.

---
#### Closure

Note:
closure as a way to “remember” and continue to
access a function’s scope (its variables) even once the function has finished running.

```js
    function makeAdder(x) {
        // parameter `x` is an inner variable
        // inner function `add()` uses `x`, so
        // it has a "closure" over it
        function add(y) {
            return y + x;
        };
        return add;
    }
```