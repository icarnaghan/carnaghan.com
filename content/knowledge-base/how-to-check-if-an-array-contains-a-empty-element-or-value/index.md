---
author: "icarnaghan"
title: "How to check if an array contains a empty element or value"
date: 2018-03-22
---

Use the following code example

```
$array = array('a','b',''); //The array to check for empty values
```

```
echo (in_array('  ', $array)) ? 'Empty values exists' :'No empty values'; ?> //Checking if empty values exist in the array
```

**NOTE**:

_**in\_array**_ = searches a array for a specific value
