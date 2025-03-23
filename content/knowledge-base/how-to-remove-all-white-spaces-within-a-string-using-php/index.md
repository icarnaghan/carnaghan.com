---
author: "icarnaghan"
title: "How to remove all white spaces within a string using PHP"
date: 2018-03-22
---

There are two functions that could be used namely **str\_replace** and  **preg\_replace**.

First, we'll give an example using **str\_replace**. **str\_replace** is the preferred method since it's faster and easier to use than **preg\_replace** which relies on regular expressions.

**str\_replace _(PHP 4, PHP 5) - http://de.php.net/manual/en/function.str-replace.php_**

```
$string =  "This is a test string";
$new_string = str_replace(' ','',$string);
echo $new_string; //This will output Thisisateststring

```

**preg\_replace** _(PHP 4, PHP 5)_ - _http://php.net/manual/en/function.preg-replace.php_

```
$string =  "This is a test string";
$new_string = preg_replace('/( *)/','',$string);
echo $new_string; //This will output Thisisateststring
```

or

```
 $string =  "This is a test string";
 $new_string = preg_replace('/\s/','',$string); // \s means strip all white spaces
 echo $new_string; //This will output Thisisateststring
```
