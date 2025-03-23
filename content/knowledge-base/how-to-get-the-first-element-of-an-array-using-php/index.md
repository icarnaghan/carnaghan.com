---
author: "icarnaghan"
title: "How to get the first element of an array using PHP"
date: 2018-03-22
---

If you have the array

```
$array = array('a','b','c','d');
```

you will need to get the value **a** from the array

**Answer**:

Use the **array\_shift** function available in PHP 4 and 5 which shifts an element off the beginning of an array. See example below

```
$array = array('a','b','c','d');
$first_element = array_shift($array);
echo $first_element;
```

The above code will output **a**
