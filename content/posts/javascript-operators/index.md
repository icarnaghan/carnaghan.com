---
author: "icarnaghan"
title: "JavaScript Operators"
date: 2018-10-14
categories: 
  - "coding"
tags: 
  - "bitesize-javascript"
  - "cmst-388"
  - "javascript"
---

JavaScript provides different kinds of operators which enable us to perform actions on given values or variables used in our code. As you develop more complex code, you will come to rely on operators for performing the various functionally you are building. Before we dive into operators, let's clear up a couple of fundamental programming terms, statements and expressions.

A statement is a line of code or action that consist of values, variables, and operators. In the last lesson you created several statements that assigned values to variables using the assignment = operator. **Statements can set values but do not become values themselves**. Statements end with a semi-colon. In contrast, an expression is a piece of code that resolves to a value, i.e. values, calculations resulting in other values, variables, and groups of variables.

Now, let's look at the different types of operators we can use in JavaScript.

## Math Operators

As with most programming languages, JavaScript uses the four most common operators:

```javascript
+ (plus)

- (minus)

/ (divide)

* (multiply)
```

In addition, the assignment operator = is used for value assignment.

## Comparison Operators

Four equality operators are available in JavaScript:

```javascript
== (loose equals)

=== (strict equals)

!= (loose not equals)

!== (strict not equals)
```

> The loose operators provide a way to compare two values of different types. For example "13" == 13 would yield true even though one is a string and one is a number.

In addition to equality operators, JavaScript provides several different comparison and logical operators:

```javascript
< (less than)

> (greater than)

<= (less than or loose equals)

>= (greater then or loose equals)
```

## Compound Operators

Compound operators are useful for writing shorthand statements such as a = a + 2, which can make use of the compound variable +=. In this example a = a + 2 would become a += 2. Compound operations are available in each of the four operators:

```javascript
+=

-=

*=

/=
```

## Increment/Decrement Operators

Increment / decrement operators work in a similar way to compound operators whereby they provide a shorthand method of writing statements to increment or decrement values. For example a = a + 1 can use an increment variable of a++. Similarly a decrement take on this would look like a--. There are two increment and decrement operators:

```javascript
++

--
```

## **→ Try it out**

Create two files called **index.html** and **script.js** and enter the code below into each. Alternatively, if you followed along in the previous lesson, use the existing script.js file and replace its content with code below. After you have updated your script.js file, examine the results produced in the browser console.

```markup
<!DOCTYPE html>
<html>
  <head>
    <title>Learning JavaScript</title>
  </head>
  <body>
    <h1>Learning JavaScript</h1>
    <script src="script.js"></script>
  </body>
</html>
```

```javascript
/**
* Operators
*/

let a = 10;
let b = 5;
let c = '5';
let d = 10;
 
// Math Operators
console.log(a + b);
console.log(b * a);
console.log(a / b);
console.log(b - a);
 
// Comparison Operators
console.log(a != b);
console.log(a == d);
console.log(b === c);
console.log(b == c);
console.log(b >= c);
 
// Compound Operators
let result= a-=1;
console.log(result);
 
let result = b++;
console.log(result);
```

> To see the results: open index.html in your browser and open the console, Press Ctrl+Shift+J (Windows / Linux) or Cmd+Opt+J (Mac).

How did you do? Were the results as you expected? Continue plugging in other values, variables and operators in order to practice these concepts further.

## Precedence and Associativity

Remember math class when you had to work out precedence of values in a calculation?

```javascript
4 + 6 * 9
(4 + 6) * 9
```

The first statement will result in 58, while the second in 90. This is due to the order in which the expressions are calculated. In the first example 6 is multiplied by 9 first and then 4 is added. The parenthesis in the second statement give precedence to 4 + 6 which are added first before multiplying by 9. The good news is that JavaScript works in the same way you use precedence in regular math. Try it out and enter both in the console.

In addition to regular math, as you've learned JavaScript has a number of other operators. Try adding the below statement to your script:

```javascript
4 + 6 > 9
```

Was the result as you expected? in JavaScript, the order of precedence of math operators is higher than that of comparison operators. Therefore the expression 4 + 6 is calculated before comparing the result to 9, resulting in true.

> Operator precedence determines the way in which operators are parsed with respect to each other. Operators with higher precedence become the operands of operators with lower precedence. So how do we keep track of what takes precedence? Thankfully, there is a very handy reference sheet included below, which lists all operators and associated precedence ranked from highest to lowest.
> 
> Operator Precedence Reference Sheet

The reference sheet also includes associativity, which lets us know the direction in which the operation is executed. For example, typical math operations will be calculated left to right as you would be used. Other operators may cause execution to happen right to left. This is the case with the assignment = operator. Take the following statement:

```javascript
let e,f;

e = f = 4 + 6

console.log(a);
console.log(b);
```

Notice that you can define more than one variable at a time in the example above. In this case the operation on the right is calculated and then at the end is assigned to b. The value of b is then assigned to a. This can be confirmed by examining at the values of a and b.

In this lesson you have learned about expressions, statements, operators, and operator precedence. The complete code used throughout this lesson is included below for your reference.

```javascript
/**
* Operators
*/

let a = 10;
let b = 5;
let c = '5';
let d = 10;
 
// Math Operators
console.log(a + b);
console.log(b * a);
console.log(a / b);
console.log(b - a);
 
// Comparison Operators
console.log(a != b);
console.log(a == d);
console.log(b === c);
console.log(b == c);
console.log(b >= c);
 
// Compound Operators
let result= a-=1;
console.log(result);
 
result = b++;
console.log(result);

// Precedence and Associativity
console.log(4 + 6 > 9)

let e,f;
 
e = f = 4 + 6
 
console.log(e);
console.log(f);
```
