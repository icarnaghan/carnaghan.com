---
author: "icarnaghan"
title: "Important Features of ES6"
date: 2019-10-16
categories: 
  - "coding"
tags: 
  - "javascript"
---

EcmaScript is the standardized scripting language that JavaScript and some other languages, like ActionScript implement. JavaScript was invented by Brendan Eich in 1995 and became an ECMA standard in 1997. ECMAScript 2015 is version 6 of the ECMA Script programming language therefore known as ES6. There are many new features in ES6 which are listed below.

## Block Scoping

The lack of block scoping created confusion in ES5. A new keyword **let** works similarly to var but the variable it declares is block-scoped and exists within the current block only.

```javascript
function TotalAmount (v) {
  var a = 0 
  if (v) {
    let a = 1 
  } 
  { 
    let a = 100     
{
      let a = 1000 
      }
  }  
  return a
}

console.log(TotalAmount(true))
```

The Output will be 0 since the if block has **let**. Otherwise, it would have been 1. Another keyword is const which is immutable and is also block-scoped like let. Const enables us to define constants.

## Classes and Modules

Classes were introduced in ES6 with support for the **class** keyword, **constructor** keyword and the **extend** keyword for inheritance. Classes in ES6 have a more convenient syntax which is helpful. Method names don’t need to have the word _function_ anymore.

```javascript
class base {
  constructor(options = {}, data = []) { 
    this.name = 'B'
    this.url = 'http://b.co'
    this.data = data
    this.options = options
  }

    getName() { 
      console.log(`Class name: ${this.name}`)
    }
}
```

Up until ES6, there were no native modules support in JavaScript. ES6 now has built-in modules, which are stored in files with one module per file. There is also support for exporting or importing values to and from modules without global namespace pollution using export and import keywords.

```javascript
//lib.js
export const sqrt = Math.sqrt;
export function sq (a) {
    return a * a;
}
export function diagonal(a, b) {
    return sqrt(sq (a) + sq (b));
}
//main.js
import { square, diag } from 'lib';
console.log(sq (9));  //81
console.log(diagonal(4, 3));  //5
```

## Template literals (Template strings)

Interpolation in JavaScript is a way to output variables in the string. Before we had to break the string using concatenation:

```javascript
var greet = 'Hello' + first + ' ' + last + '.'
In ES6 we use ${var} inside back-ticked string like:
var greet = `Hello ${first} ${last}.`
```

For multi-line strings before ES6, we accomplished this by:

```javascript
var hey = 'How \n\t'
    + 'are \n\t'
    + 'you \n\t'
In ES6:
var hey = `How
    	     are
    	     you`
```

## Destructuring

Destructuring is a JavaScript expression that enables the extraction of elements from an array and assigns them to the variables. Pre-ES6 we would have accomplished this with the following code:

```javascript
var intro = ["Hello", "How" , "are", "you"];
    var a = intro [0];
    var b = intro [3];

    console.log(a);   //"Hello"
    console.log(b);      //"you"
```

In the above example we made two different variables to store the elements. In ES6 you can accomplish destructuring using the easier process below:

```javascript
var [a, b] = ["Hello", "How" , " are ", " you "];

    console.log(a);     //"Hello"
    console.log(b);     //"How"
```

or this way:

```javascript
var intro = ["Hello", "How" , "are", "you"];
    var [a, b] = intro;

    console.log(a);//"Hello"
    console.log(b);//"How"
```

## Default Parameters

In ES6, you can use default parameter values by specifying an equal sign which is used when the caller doesn’t provide a value for the parameter.

```javascript
function fun (a, b=0) {
    return [a, b];
}
fun(1);      //[1,0]
```

here we have assigned the default value of b to 0.

## Arrow Functions

Arrow functions were introduced in ES6 in order to provide a concise way to write functions in JavaScript. The context inside the arrow function is lexically defined. The arrow => sign is used for making arrow functions. Below is an example of calling the UpperCase function in ES5:

```javascript
var UpperCase = function() {
  var _this = this

  this.string = this.string.toUpperCase()
  return function () {
    return console.log(_this.string)
  }
}

UpperCase.call({ string: 'es6' })() 
```

In ES6 we can write this same function in the following way:

```javascript
var UpperCase = function() {
  this.string = this.string.toUpperCase()
  return () => console.log(this.string)
}

UpperCase.call({ string: 'es6 ' })()
```

Before ES6 every new function defined its this value based on how the function was called. Arrow functions bring more clarity and readability to the code but there are some important points to keep in mind:

- Arrow functions cannot be used as constructors and will throw an error when used with the **new** operator.

- Arrow functions do not have a prototype property.

- Arrow functions cannot be used as generators.

## Promises

A promise is a placeholder for a value not necessarily known when the promise is created. Promises provide a way to handle results and errors. They greatly simplify asynchronous programming by making the code look synchronous and avoid problems associated with callbacks. A callback is a mechanism in which a function may be passed as a parameter to another function. A promise can be in three states:

- **Pending**: which is the initial state

- **Fulfilled**: when the operation is completed successfully

- **Rejected**: when the operation is failed.

Promise properties are promise.length, whose value is the number of constructor arguments and promise.prototype which represents the prototype for the Promise constructor.

Creating a promise:

```javascript
const myPromise = new Promise((resolve, reject) => {

});
```

Methods that are used with promises are:

- Promise.all(iterable): waits for all promises to be resolved, or for any to be rejected.

- Promise.allSettled(iterable): Wait until all promises have settled

- Promise.race(iterable): Wait until any of the promises are resolved or rejected.

- Promise.reject(reason): Returns a new Promise object that is rejected for the given reason.

- Promise.resolve(value): Returns a new Promise object that is resolved with the given value.

ES6 has provided many advantages to JavaScript users. In ES6 tail call optimization has been enabled. Shorthand syntax for object literals, usage of asynchronous functions and generators and import statement feature are also implemented in ES6. When ES6 was released, there were a number of compatibility issues that had to be resolved using browser tools coding hacks. Nowadays however ES6 has become mainstream and the benefits it brings can easily be implemented into your workflow and projects without fear of breaking browser compatibility.
