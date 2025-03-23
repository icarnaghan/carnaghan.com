---
author: "icarnaghan"
title: "JavaScript Loops"
date: 2018-12-20
categories: 
  - "coding"
tags: 
  - "bitesize-javascript"
  - "cmst-388"
  - "javascript"
---

Often in programming, we need to carry out similar instructions a number of different times. Loops help reduce redundant code and let you quickly offload repetitive tasks to the computer. In JavaScript there are several types of loops. In this lesson we are going to examine while, do while, and for loops.

## While and Do While loops

As their names suggest, while and do while loops carry out a number of tasks 'while' a certain condition is true. Take for example the need to display a series of  numbers each incrementing by 1 until it we reach a certain limit (10). This could be carried out by writing the following code:

```javascript
console.log(1);

console.log(2);

console.log(3);

console.log(4);

console.log(5);

console.log(6);

console.log(7);

console.log(8);

console.log(9);

console.log(10);
```

Alternatively, instead of writing ten lines of code, we could use a loop that would repeat the process of incrementing the number by 1 each time and displaying it in the console. Let's take a look at what this might look like using a while loop.

```javascript
let x=1;

while(x <= 10) {

  console.log(x);

  x++;

}
```

First of all we are initializing our x variable, which will serve as the 'counter' in the loop. It is important to keep track of the counter in order to complete the correct number of repeating instructions and to exit the loop when the criteria is no longer valid, i.e. when x is no longer less than or equal to 10. In this example we are using x++ to increment x by one each time the loop completes. By its very nature a while loop will repeat until the criteria specified in the parenthesis (x <= 10). In contrast to a while loop, a do while loop will execute first time regardless of whether or not the condition is met. This is handy in circumstances where there is a requirement to run the loop at least one time. Take for example if our x variable already = 10. If this is the case, our while loop will never execute. By using a do while loop we guarantee at least one run beyond the criteria failing.

```javascript
let x = 10;

do {
  console.log(x);
  x++;
} while (x <= 10);
```

In the code above, the **do** part of the loop will run one time and then stop as the **while** criteria x <= 10 is not met.

## For Loops

For loops provide a nice way to package up a while loop without having to write the iterator within the loop itself. Take for example the above while loop example, which can be simplified in a for loop.

```javascript
for (let x=1; x <= 10; x++) {

  console.log(x);

}
```

If a for loop only has one line of code returned, it can be further simplified by removing the curly braces.

```javascript
for (let x=1; x <= 10; x++) console.log(x);
```

A for loop expects three different parameters, an initializer (x=1), a criteria x <=1, and an iterator x++. The criteria can be left out but there should be some mechanism in the loop to eventually break out of the loop or you may run into a situation where you get stuck in an infinite loop. Take for example the following for loop without a criteria specified in the for statement.

```javascript
for (let x=1; x++;) {
    if (x>10) {
        break;
    }
    console.log(x)
}
```

Here we are evaluating x within a conditional statement. This can sometimes be a convenient way to write loops based on a more complex criteria. There are other ways to iterate over data using JavaScript such as the foreach method. We will be covering this in a later lesson along with arrays and objects.
