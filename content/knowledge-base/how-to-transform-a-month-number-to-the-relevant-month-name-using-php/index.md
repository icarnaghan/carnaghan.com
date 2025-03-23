---
author: "icarnaghan"
title: "How to transform a month number to the relevant month name using PHP"
date: 2018-03-22
---

This can be obtained by combining the _**date**_ function with the _**mktime**_ function

For example if I want to get **Jan** from the number **1** which represents the **first month**in the **year** I would use something similar to the below

```
$i = 1; //The number 1 represents January
 
echo date("M",mktime(0,0,0,$i,1,2010)); //This will output Jan

```

So if you want to output **Feb** the value of $i would be 2 etc

**USAGE**:

**date** = string **date** ( string $format \[, int $timestamp \] ) **_(PHP 4 & 5)_**

**mktime** = int **mktime** (\[ int $hour = date("H") \[, int $minute = date("i") \[, int $second = date("s") \[, int $month = date("n") \[, int $day = date("j") \[, int $year = date("Y") \[, int $is\_dst = -1 \]\]\]\]\]\]\] )  **_(PHP 4 & 5)_**
