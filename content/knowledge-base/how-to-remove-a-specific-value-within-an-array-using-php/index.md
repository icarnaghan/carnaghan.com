---
author: "icarnaghan"
title: "How to remove a specific value within an array using PHP"
date: 2018-03-22
---

If you have an array and you wish to remove the **"None"** values in the array you can use the method below, please replace the **"None"** value with the value you need to remove from the array

```
$array = array("Apple","Orange","None"); //The array

//Removing all None values from the array
 
foreach (array_keys($array, 'none') as $key) {
 
    unset($array[$key]);
 
}

print_r($array); //This will output the array without the value None
```
