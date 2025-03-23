---
author: "icarnaghan"
title: "JavaScript Functions"
date: 2018-12-22
categories: 
  - "coding"
tags: 
  - "bitesize-javascript"
  - "cmst-388"
  - "javascript"
---

Functions are repeatable blocks of code. They are fundamental to most programming languages and allow you to build applications with reusable code that can be called with different arguments. The best way to explain functions is through an example. Suppose you wanted a quick way to calculate how much your bill would be with tip (assume for this example the bill amount includes tax).

## **→ Try it out**

Create two files called **index.html** and **script.js** and enter the code below into each. Alternatively, if you followed along in the previous lesson, use the existing script.js file and replace its content with code below.

```javascript
<!DOCTYPE html>
<html>
  <head>
    <title>Bitesize JavaScript</title>
  </head>
  <body>
    <h1>Bitesize JavaScript</h1>
    <script src="script.js"></script>
  </body>
</html>
```

```javascript
/**
* Functions
*/

// Define tip calculator function
function calculateTotalPrice(bill, tip) {
  return bill * (tip + 1);
}

// Call tip calculator function and store in a variable
let jamesCost=calculateTotalPrice(22.00, .15)
let karenCost=calculateTotalPrice(34.87, .20)
let clareCost=calculateTotalPrice(28.98, .18)

console.log("James owes: $" + jamesCost.toFixed(2))
console.log("Karen owes: $" + karenCost.toFixed(2))
console.log("Clare owes: $" + clareCost.toFixed(2))
```

> To see the results: open index.html in your browser and open the console, Press Ctrl+Shift+J (Windows / Linux) or Cmd+Opt+J (Mac).

## Function Declaration

In the above example, we have defined a new function called **calculateTotalPrice**, similar to how we have previously given variables a name. A function can also accept values that get passed into it called arguments. The **calculateTotalPrice** function accepts two arguments, bill and tip. The bill argument simply represents a bill that a customer may receive at a restaurant, while tip is the percentage the customer is willing to add. The purpose of the function is to calculate the total cost of the meal by adding the desired tip amount. With both the bill and tip, the function can then carry out its calculation to generate the total amount.

### Calling the Function

In order to call the function we simply provide the name of the function and include its arguments in parenthesis. In the example above we go one step further and store the result of the function call to a variable. Note the function is being called three different times for three different individuals who have all ordered dinner and want to calculate their final cost. You can quickly see the power behind functions is tied to their reuse without having to repeat code multiple times.

> Did you notice the .toFixed() code included in the example above? JavaScript has many built in methods for formatting numeric data. The .toFixed method simply provides a quick way to define the number of digits after the decimal point (in this case we use 2 for currency).

## Function Expression

Functions are commonly written as expressions, whereby a variable is defined and set to the returning value of the function itself. This is better explained in an example.

```javascript
let calculateTotalPriceExpression = function(bill, tip) {
  return bill * (tip + 1);
}; // Note: a semi-colon is required after a function expression
```

In the above example, the function will behave in a similar manner to our function declaration above. The difference is that it is written as an expression where calculateTotalPrice has resulted in the value calculated from the function. One of the biggest differences between writing a function as a declaration or statement vs writing it as an expression is the flow of control or order in which everything is processed in your script.

> Function expressions cannot be called earlier in the code before they are defined. In contrast to this, function declarations can be called anywhere regardless of ordering.

Review the following examples.

```javascript
console.log (calculateTotalPrice(22.00, .15).toFixed(2)) // This code will work
console.log (calculateTotalPriceExpression(34.87, .20).toFixed(2)) // This code will fail

// Define tip calculator function
function calculateTotalPrice(bill, tip) {
  return bill * (tip + 1);
}

// Define tip calculator function expression
let calculateTotalPriceExpression = function(bill, tip) {
	return bill * (tip + 1);
}
```

Here we see the first call to calculateTotalPrice succeed and yield the correct amount. The second console.log function will fail because calculateTotalPriceExpression has not yet been defined and will result in an error similar to

Uncaught ReferenceError: calculateTotalPriceExpression is not defined

## Arrow Functions

In the newer ECMAScript6 JavaScript engine, function expressions can be written in a shorter form called Arrow Functions. Let's take a look at a simple temperature conversion function.

```javascript
let toCelsius = (fahrenheit) => {
  return (5/9) * (fahrenheit-32);
};
```

In an arrow function, if there is only one line or single expression to return within the function, it can be further shortened by removing the surrounding curly braces and the return keyword. In addition to this, if only one argument is present, the surrounding parenthesis can also be removed.

```javascript
let toCelsius = (fahrenheit) => (5/9) * (fahrenheit-32);
let toCelsius = fahrenheit => (5/9) * (fahrenheit-32); // Same as the function above except parenthesis can be omitted in situations where only one argument exists
```

Arrow functions with no arguments are written with empty parenthesis.

```javascript
let warninglog = () => console.log("warning");
```

> For more on Arrow functions see ECMAScript6 New Features.

In JavaScript you have three ways to write functions, declarations, expressions, and arrow functions. How you write your own functions will depend on your own projects, however for the remainder of these introductory lessons, we will be sticking mostly to function declarations. You should now have a good understanding of functions within JavaScript and the different ways they can be defined.
