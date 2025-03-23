---
author: "icarnaghan"
title: "Strings"
date: 2012-06-16
categories: 
  - "coding"
tags: 
  - "developing-with-php"
---

PHP provides many different functions for manipulating strings.  Some of the more common functions are provided here, however for a full listing of all the available string functions see http://www.php.net/manual/en/ref.strings.php.<!--more-->

The notes below summarize the string basics including defining and creating strings as well as a table containing common string functions which are useful in everyday programming.

#### String Basics

Strings can be created and accessed by defining a new variable, for example:

$mystring = 'hello world';

In this example, single quotes are used.  Double quotes can also be used when other variable values are needed to be displayed in the string and when special characters are required.  Variables can be placed in curly brackets {} to distinguish it from the rest of the string.  Special characters need to be escaped by using the character:

$mystring = "hellot{$user}"  \\ t inserts a tab space and $user is a variable.

Below is a list of the most common escape sequences that can be used with double quoted strings.

Delimiters can be used instead of single and double quotes, especially useful in situations where a long string is needed that may include instances of single and double quotations.  Heredoc can be used to provide the same functionality as double-quotes and Nowdoc can be used to provide the functionality of single-quotes.  For example:

$mystring = <<<DELIMITER (String goes in here) DELIMITER;

The above example uses Heredoc.  To use Nowdoc, simply enclose the DELIMITER in single-quotes.

#### Common String Functions

Search Strings

**\[table id=5 /\]**

Replacement Strings

\[table id=6 /\]

PHP also provides case-insensitive versions of many string functions.  A few are listed below:

- strstr() - Case Insensitive version: stristr()
- strpos() - Case Insensitive version: stripos()
- strrpos() - Case Insensitive version: strripos()
- str\_replace() - Case Insensitive version: str\_ireplace()

For more information on case-insensitive versions of PHP string functions, visit php.net.

#### Formatting Strings

print\_f is a powerful PHP function which allows for conversions within strings.  Conversions occur by using a type specifier (shown in the table below).  The type specifier(s) are then converted once code is executed.  A simple example follows:

print\_f("%d times %d is %d.", 2, 3, 2\*3);

This is an example from the Wrox book which demonstrates three type specifiers d% within a string in quotes.  After the quotes three parameters define the values that will be placed at the type specifiers.  In this case %d is used, which will mean the value will be converted as an integer presented in decimal format.  A list below shows the different type specifiers that can be used (source: http://php.net/manual/en/function.sprintf.php):

- _%_ - a literal percent character. No argument is required.
- _b_ - the argument is treated as an integer, and presented as a binary number.
- _c_ - the argument is treated as an integer, and presented as the character with that ASCII value.
- _d_ - the argument is treated as an integer, and presented as a (signed) decimal number.
- _e_ - the argument is treated as scientific notation (e.g. 1.2e+2). The precision specifier stands for the number of digits after the decimal point since PHP 5.2.1. In earlier versions, it was taken as number of significant digits (one less).
- _E_ - like _%e_ but uses uppercase letter (e.g. 1.2E+2).
- _u_ - the argument is treated as an integer, and presented as an unsigned decimal number.
- _f_ - the argument is treated as a float, and presented as a floating-point number (locale aware).
- _F_ - the argument is treated as a float, and presented as a floating-point number (non-locale aware). Available since PHP 4.3.10 and PHP 5.0.3.
- _g_ - shorter of _%e_ and _%f_.
- _G_ - shorter of _%E_ and _%f_.
- _o_ - the argument is treated as an integer, and presented as an octal number.
- _s_ - the argument is treated as and presented as a string.
- _x_ - the argument is treated as an integer and presented as a hexadecimal number (with lowercase letters).
- _X_ - the argument is treated as an integer and presented as a hexadecimal number (with uppercase letters).

Optional sign, padding, alignment, width and precision specifiers can be used, which are described in more depth at php.net.

**sprintf()** is essentially the same as print\_f except rather than printing the result, it returns it so that it can be used as a variable for further processing.

**Additional formatting of strings can be done with PHP's built in trimming functions:**

- trim() removes white space from the beginning and end of a string
- ltrim() removes white space only from the beginning of a string
- rtrim() removes white space only from the end of a string

All of these can be useful when dealing with user-entered form data.  All of them accept a string and then trim it.  An optional parameter can be passed - a string of characters to treat as white space.

str\_pad(), wordwrap() and number\_format() are three additional commonly used formatting functions that can be easily used in code.  More information on these is available at php.info at the relevant links.
