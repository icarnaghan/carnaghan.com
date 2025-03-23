---
author: "icarnaghan"
title: "How to remove the first element of an array using PHP and then storing the element in a variable"
date: 2018-03-22
---

- By using the PHP function '**array\_shift**' we can remove the first value of an array
    - **array\_shift** \- _Shift an element off the beginning of array (PHP 4 & 5)_

**Example**:

```
$array = array("apple","peach","pineapple","banana");
$first_element = array_shift($array);

echo '<pre>';
print_r($array);
echo '</pre>';

echo $first_element;
```

In the above example we have an array with 4 values, now using the '**array\_****shift**' function we remove the first value namely _**apple**_ and store it in the **$first\_element** variable.

Now if we print the contents of **$array** we'll notice there are only 3 values left namely **peach**, **pineapple** and **banana** and **apple** belongs to the **$first\_element** variable.

**Output from example:**

```
//Contents of $array
Array
(
    [0] => peach
    [1] => pineapple
    [2] => banana
)

//Value of First Element
apple
```
