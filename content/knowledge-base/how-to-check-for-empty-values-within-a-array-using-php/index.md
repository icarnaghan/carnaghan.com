---
author: "icarnaghan"
title: "How to check for empty values within a array using PHP"
date: 2018-03-22
---

If you have an array called **$array** with the below values

```
Array
(
    [0] => 1299016800
    [1] => 
    [2] => 
)
```

As we can see in the above example we have **2 empty values** within the **array**, now how do we determine this using **PHP**

First we get the **size** of the **array**

```
$mainSize = sizeof($array);
```

Now we get the **size** of the **array** without the **empty values**

```
$emptySize =sizeof(array_filter($array));
```

Now we **compare** the **2 different sizes**, if they are equal to each other, then it means that there aren't **empty** **values** within the **array**, else there are **empty values** within the **array**

```
$mainSize = sizeof($array);
$emptySize =sizeof(array_filter($array));
 
if($mainSize == $emptySize){
              echo 'Array not empty';
}else{
              echo 'Array is empty';
}
```
