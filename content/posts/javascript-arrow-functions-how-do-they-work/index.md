---
author: "icarnaghan"
title: "JavaScript Arrow Functions: How Do They Work?"
date: 2019-09-23
categories: 
  - "coding"
tags: 
  - "javascript"
---

ES6 introduced a number of exciting features to the JavaScript standard classes, string templates, array and object de-structuring, block-scope variable declarations with "let" and "const", and perhaps the most visible new feature, arrow functions. Arrow functions have quickly become the standard way of writing functions among professional JavaScript developers. Because they are so widespread, it's essential for every JavaScript programmer to understand arrow functions - what they are, how to write them, and how they are different from ordinary functions.

As the name suggests, arrow functions are written with the "fat arrow" construct, =>. Like ordinary functions declared with the "function" keyword, arrow functions take in some input and produce some output. These are equivalent functions:

```javascript
function (input) {      
    return input + 5;  
}
```

```javascript
(input) => { return input + 5; }
```

Unlike normal functions, arrow functions may have an implicit return value. If the "return" keyword is not used, the JavaScript compiler will infer what value should be returned. Therefore the arrow function above may be written even more concisely as:

```javascript
input => input + 5;
```

Arrow functions, unlike normal functions, are always anonymous, so they must be assigned to a variable in order to be used. This could be explicit, such as "const addFive = input => input + 5;", or implicit by passing an arrow function as an argument to another function. This is where the true benefit of arrow functions is seen, when combined with JavaScript's rich variety of built-in array and string manipulation functions:

```javascript
const myArray = [1, 2, 3, 4, 5];
const myArrayDoubled = myArray.map(number => number * 2);

console.log(myArrayDoubled) // [2, 4, 6, 8, 10]
```

The arrow function notation helps keep this code very readable and maintainable when compared with the pre-ES6 way of writing such a function:

```javascript
 myArray.map(function(number) { return number * 2 })
```

Arrow functions differ from ordinary functions in one very important way: when written inside an object, an arrow function has "lexical 'this'," while an ordinary function has "dynamic 'this'". This means that, inside an arrow function, the "this" keyword always refers to the object the arrow function belongs to - the meaning of "this" is determined by where the arrow function is written. On the other hand, inside normal functions, the "this" keyword refers to the object the function it is called on - not necessarily the same as the object it belongs to! Consider this example:

```javascript
function NormalFlower(petals) {     
    this.petals = petals; // pick a petal    
    function pickPetal() {    
        this.petals--;    
    };
    pickPetal();
}
```

```javascript
function ArrowFlower(petals) {     
    this.petals = petals; // pick a petal
    pickPetal = () => { 
        this.petals--;
    };
    pickPetal();
}
```

```javascript
const normalFlower = new NormalFlower(5);
const arrowFlower = new ArrowFlower(5);
console.log(normalFlower.petals, arrowFlower.petals);

// 5 4
```

While it looks like both objects should do the same thing - initializing a new Flower object with 5 petals, then immediately picking a petal - only the ArrowFlower object worked properly! The reason for this is because the NormalFlower object, which was used a normal function, the "this" keyword inside pickPetal() actually referred to **the scope in which it was executed** - in this case, the global scope.

Not only did it not pick a petal as expected, but now the global "window" object unexpectedly has a "petals" property (of type Number and value NaN - not a number - because it did not have valid numeric value to decrement). JavaScript programmers have traditionally worked around this oddity by either passing in the proper "this" object as a parameter, or by using Function.prototype.bind(this) - but with ES6 arrow functions, these workarounds are now unnecessary. In arrow functions, the "this" keyword always refers to the scope where the function is written.

Arrow functions are one of the many powerful new features found in ES6 JavaScript. They are especially useful for short functions that do simple work, to pass as callback functions, or in cases where the "this" keyword should always refer to the function's parent object. Every JavaScript developer should learn arrow functions and use them regularly.
