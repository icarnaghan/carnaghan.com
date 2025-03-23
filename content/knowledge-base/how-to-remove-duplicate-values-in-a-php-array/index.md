---
author: "icarnaghan"
title: "How to remove duplicate values in a PHP array"
date: 2018-03-22
---

1. Use the **array\_unique** function
    - **array\_unique** _(PHP 4 >= 4.0.1, PHP 5)_
    - **array\_unique** _(Takes an input array and returns a new array without duplicate values__)_
    - **array\_unique** _(array $array \[, int $sort\_flags\=SORT\_STRING \] )_

**Example**:

**CODE:**

_**<?php**_

> _//Array with duplicate values_ $array = array("test","test1","test","sum","minus","max","max","max","min");
> 
> _//Removing duplicate values_ $newArray = **array\_unique**($array);
> 
> echo '<pre>'; print\_r($newArray);

_**?>**_ 

**OUTPUT:

**

_//The above code will produce the following results_ _without the duplicate values_ **Array (**

> **\[0\] => test** **\[1\] => test1** **\[3\] => sum** **\[4\] => minus** **\[5\] => max** **\[8\] => min**

**)**
