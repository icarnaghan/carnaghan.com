---
author: "icarnaghan"
title: "Conditional Statements and Looping"
date: 2012-06-03
categories: 
  - "coding"
tags: 
  - "developing-with-php"
---

Conditional statements (or decisions) and loops make up a good portion of programming code in general.  I am familiar with these concepts though other languages, however I have never programmed them in PHP.  This week I have been reviewing the first 5 chapters of Beginning PHP 5.3, which has been giving me a good solid introduction to PHP.

<!--more-->

Chapter 4 focuses specifically on decisions and loops.  I am including some of the highlights from this chapter here, specifically example code on the various type of decisions and loops that can be used in PHP.

#### Decisions

PHP has three main ways of writing an if statement.  The first is the common if / elseif / else statement, the second includes the common switch statement.  Both of these I am already familiar with in other languages, however the syntax in PHP is new to me.  The third method is called a Ternary Operator, which is completely new to me.  This basically lets you shorthand a basic if / else statement (I can see how it would come in handy).  The ternary operator uses three expressions, the first is the decision expression, the second is an expression that is returned if expression 1 is true.  If expression 1 is not true then expression 3 is returned.

\[table id=3 /\]

Note: When using a switch statement, a break is necessary to stop the execution of following case statements.  Once a value is true PHP continues to execute all remaining code in the statement unless told otherwise.

#### Looping

PHP supports three types of loops.  While, do while and for loops.  While loops continue to execute while a value is within a set condition.  An expression is tested at the beginning of the loop.  For example while number < 10.  Once the number reaches 10 (via an incremental statement inside the loop), the loop will stop.  So on the last run the number was 9 and at the end of the statement it is incremented by 1, the loop will no longer execute.  A do while loop on the other hand runs the loop first and then checks for the condition.  This means that if a condition is incremented at the end of the loop from 9 to 10, the loop will run one last time as the expression will not be tested again until the end of the next loop.

A for loop allows for neater code and should be used when you know how many times you want to repeat the loop.  A counter variable can be used, which keeps track of how many time the loop has executed.  This means you do not have to place an incremental statement inside the loop as with a while loop.  A for loop includes an initializer, loop test and counting expression.  Example: for ( $variable = 1; $variable < 10; $variable++ ).

\[table id=4 /\]

It should be noted both decisions and loops can be nested easily using PHP.  For example:

```
if ( $variable > 1 ) {
  { if  ( $variable < 10 ) {
    // run code
  }
}
```

Decisions and loops are also often nested and mixed with each other, which will be explored in more depth later on.
