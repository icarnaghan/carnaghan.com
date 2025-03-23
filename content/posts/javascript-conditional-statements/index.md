---
author: "icarnaghan"
title: "JavaScript Conditional Statements"
date: 2018-10-20
categories: 
  - "coding"
tags: 
  - "bitesize-javascript"
  - "cmst-388"
  - "javascript"
---

Conditional statements (commonly called if statements) provide a way for JavaScript to make decisions and run specified code based on a set of criteria. In JavaScript, the criteria or condition is surrounded in parenthesis and the resulting code to run is contained in a block. Up until now, we have been examining single line statements. In JavaScript, a block of code is surrounded by curly braces. Let's look at an example.

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
* Conditional Statements
*/

// Simple date conditional
let currentDate = new Date();
if ( currentDate.getDay() > 4) {
  console.log('It is the weekend!');
}
```

In this example we are using the built in JavaScript date function in order to retrieve the current day. See JavaScript Date Methods for more information on this function. We will look more at functions in a future lesson, but for now all you need to understand is that new Date() sets our currentDate variable to the current date and time. We use the built in .getDay to retrieve the day of the week (which is a number 0 - 6 starting at Sunday). In our code example we use a conditional statement to determine if the day is greater than 4. Because .getDay only provides values from 0-6 and 5 & 6 both represent Saturday and Sunday, it is safe to assume any values falling in this range will be the weekend. We then write the code we want our conditional statement to return if true.

> To see the results: open index.html in your browser and open the console, Press Ctrl+Shift+J (Windows / Linux) or Cmd+Opt+J (Mac).

## Boolean Conditionals

In some situations, we will want to be more specific and perhaps define a range of acceptable values that will drive our result. Boolean operators are commonly used in conditional statements and can provide a powerful way of controlling you code and expected outcomes. Suppose for example we would like to only return true when we are currently in a weekday. If we were to use less than 5 our results would erroneously report Sunday as a weekday, which has the assigned value of zero. In this situation, we need to be more specific. Take a look at the example below and try this in your console:

```javascript
/**
* Conditional Statements
*/

let currentDate = new Date();

// Simple date conditional
if ( currentDate.getDay() > 4) {
  console.log('It is the weekend!');
}

// Boolean conditionals
currentDate = new Date(); 
if ( currentDate.getDay() > 0 && currentDate.getDay() < 5) { 
  console.log('It is a week day!'); 
}
```

In the example we are using the 'and' boolean which is represented by &&. You were introduced to the and boolean operator in the last lesson. In this example we are able to determine if the current day falls between Monday and Friday and if it does, the message, "It is a week day!" is sent to the console.

```javascript
&& (True if all conditions are true)

|| (or - True if one condition is true)

! (not - Inverts true/false value)
```

There are three different boolean operators available illustrated above. The & and || are most commonly used in conditional statements and combined with else and else if (covered below), can yield a lot of flexibility in your coding of conditional statements.

## If, Else and Else If

JavaScript provides us with a way to execute code if a condition is not true. This is referred to as 'else'. Let's revisit the example above. Try modifying the boolean conditionals part of your script to use the following code and then inspect the results in your browser's console:

```javascript
/**
* Conditional Statements
*/

let currentDate = new Date();

// Simple date conditional
if ( currentDate.getDay() > 4) {
  console.log('It is the weekend!');
}

// Boolean conditionals
currentDate = new Date(); 
if ( currentDate.getDay() > 0 && currentDate.getDay() < 5) { 
  console.log('It is a week day!'); 
}
else {
  console.log('It is not the weekend yet!');
}
```

Another helpful feature of conditional statements is 'if else'. Let's assume you would like to provide which day it is if it is the weekend. To do this, we will extend the example above:

```javascript
/**
* Conditional Statements
*/

let currentDate = new Date();

// Simple date conditional
if ( currentDate.getDay() > 4) {
  console.log('It is the weekend!');
}

// Boolean conditionals
currentDate = new Date(); 
if (currentDate.getDay == 6) {
  console.log('It is the weekend and it is Sunday!');
}
else if ( currentDate.getDay() > 0 && currentDate.getDay() < 5) { 
  console.log('It is a week day!'); 
}
else { 
  console.log("It is the weekend and its Saturday!"); 
}
```

## The Ternary Operator

The if else statement can be written in one line of code using the ternary operator. Take a look at the code below which is refactored from our earlier weekend / weekday example:

```javascript
let currentDate = new Date();
currentDate.getDay() > 4
  ? console.log('It is the weekend!')
  : console.log('It is not the weekend yet!');
```

In this example we are writing our if / else statement using the ternary operator, which as you can see can reduce the amount of code we write for the same result. The conditional statement is defined with the ? which represents the if part of the code. The colon : represents the code executed if the condition did not return true.

> The ternary operator gets its name from fact that it is broken into three parts, the condition, the if block, and the else block. It is commonly used to simplify / reduce code needed for reproducing the standard if / else statement.

We could also just store the values returned from a ternary operator into a variable. For example:

```javascript
let weekend = currentDate.getDay() > 4
  ? 'It is the weekend!'
  : 'It is not the weekend yet!';
```

There is another way to reduce the amount of code needed for conditional statements, which become valuable as the amount of conditions increase. We will explore this next.

## Case Statements

Case Statements provide a more structured way of writing conditionals that have a number of different items to evaluate. Let's go back to the example we looked at earlier where we provided the day of the week only if the current data was on the weekend. What if we wanted to rewrite this statement to include the current day if it was not the weekend. We could write a lot of 'else ifs', however this is where the case statement helps bring some structure. Try the example below in your console:

```javascript
let currentDate = new Date();

switch(currentDate.getDay()) {
  case 1:
    console.log('It is Monday!');
    break;
  case 2:
    console.log('It is Tuesday!');
    break;
  case 3:
    console.log('It is Wednesday');
    break;
  case 4:
    console.log('It is Thursday');
    break;
  case 5:
    console.log('It is Friday');
    break;
  default:
    console.log('It is the weekend!');
}
```

Notice that the case statement uses a switch function that takes in a value to compare against. In this case we are providing the current day of the week. We then write our conditional expressions within the cases that follow. We know that the day of the week provided by JavaScript's Date function gives us a number between 0-6 representing the days Sunday-Saturday. We can then write each case to provide the relevant output to the console. The default value is provided if none of the previous case statements are true. In this case if the current day of the week is not Monday (1), Tuesday (2), Wednesday (3), Thursday (4), or Friday (5), we must be either in Saturday (6), or Sunday (0), which would leave result in a message stating "It is the weekend!".

> Notice that the break command is included in each case. This is needed, otherwise (even if returned true), JavaScript will continue to evaluate the remaining case statements.

We can also use case statements for evaluating different conditions within each case. To do this we simply set the switch as 'true' and then provide the different conditions for each case. Take a look at the example below:

```javascript
let currentDate = new Date();

switch(true) { 
  case currentDate.getDay() > 0 && currentDate.getDay() < 5:
    console.log('It is a weekday!'); 
    break; 
  case currentDate.getDay() = 5: 
    console.log('It is Saturday!'); 
    break; 
  default: console.log('It is Sunday!'); 
}
```

Case statements provide a structured way of handling multiple conditions. They should be used carefully as they are one of those features in JavaScript that can become abused if not implemented correctly. Often there are better ways of handling multiple conditions, which you will learn about as you develop your coding skills.

The complete code used throughout this lesson is included below for your reference.

```javascript
/**
* Conditional Statements
*/

let currentDate = new Date();

// Simple date conditional
if ( currentDate.getDay() > 4) {
  console.log('It is the weekend!');
}

// Boolean conditionals
currentDate = new Date(); 
if (currentDate.getDay == 6) {
  console.log('It is the weekend and it is Sunday!');
}
else if ( currentDate.getDay() > 0 && currentDate.getDay() < 5) { 
  console.log('It is a week day!'); 
}
else { 
  console.log("It is the weekend and its Saturday!"); 
}

// Ternary operator
currentDate.getDay() > 5
  ? console.log('It is the weekend! (Ternary)')
  : console.log('It is not the weekend yet! (Ternary)');

let weekend = currentDate.getDay() > 5
  ? 'It is the weekend! (Ternary)'
  : 'It is not the weekend yet! (Ternary)';

console.log(weekend);

/**
* Case Statements
*/

// Basic case statement
switch(currentDate.getDay()) {
  case 1:
    console.log('It is Monday!');
    break;
  case 2:
    console.log('It is Tuesday!');
    break;
  case 3:
    console.log('It is Wednesday');
    break;
  case 4:
    console.log('It is Thursday');
    break;
  case 5:
    console.log('It is Friday');
    break;
  default:
    console.log('It is the weekend!');
}

// Case statement comparing values
switch(true) { 
  case currentDate.getDay() > 0 && currentDate.getDay() < 5: 
    console.log('It is a weekday!'); 
    break; 
  case currentDate.getDay() = 5: 
    console.log('It is Saturday!'); 
    break; 
  default: console.log('It is Sunday!'); 
}
```

In this lesson you have learned about the various types of conditional statements you can use in JavaScript.
