---
author: "icarnaghan"
title: "How to remove all 0's (zeros) from an PHP array"
date: 2018-03-22
---

If I have the following PHP array

```
$array = array(9,0,6,4,5,0,9,0,0,0);
```

and I need to have all 0's removed from it.

Use the PHP **array\_filter** function. If you don't supply a callback function it will filter out all values that are equal to false

```
$new_array = array_filter($array);
```
