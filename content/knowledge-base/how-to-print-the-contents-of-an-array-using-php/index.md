---
author: "icarnaghan"
title: "How to print the contents of an array using PHP"
date: 2018-03-22
---

_//Array example_ $arr = array('one','two','three','four');

Use the **print\_r** function.

Example: **print\_r($arr);**

The example above will print out the following: **Array ( \[0\] => one \[1\] => two \[2\] => three \[3\] => four )**

**NOTE**: If you want to have the **contents** of the **array** displayed in a more readable format, add a **echo '<pre>';** statement before calling the **print\_r** function.

Example of the results:

```
Array
(
    [0] => one
    [1] => two
    [2] => three
    [3] => four
)
```

**Explanation**:

**print\_r** - Prints human-readable information about a variable (PHP 4, PHP 5)
