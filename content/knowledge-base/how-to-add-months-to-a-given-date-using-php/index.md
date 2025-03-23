---
author: "icarnaghan"
title: "How to add months to a given date using PHP"
date: 2018-03-22
---

By using the **PHP** functions **_date_** and **_strtotime_** this can be accomplished.

Example 

```
$date = '2010-03-22'; 
 
$new_date = date('Y-m-d',strtotime('+4 months',strtotime($date))); 
 
echo $new_date; //Displays 2010-07-22
```

**Explanation of PHP functions**:

_**1)**_

**FUNCTION** date

**DESCRIPTION** string **date** ( string $format \[, int $timestamp \] )

**PARAMETERS USED IN THIS EXAMPLE**

**Y** = A full numeric representation of a year, 4 digits (Examples: _1999_ or _2003_) **m** \= Numeric representation of a month, with leading zeros (_01_ through _12_) **d** \= Day of the month, 2 digits with leading zeros (_01_ to _31_)

_**2)**_

**FUNCTION** strtotime

**DESCRIPTION** int **strtotime** ( string $time \[, int $now \] )

**PARAMETERS**

**_time_** The string to parse. Before **PHP** 5.0.0, microseconds weren't allowed in the time, since PHP 5.0.0 they are allowed but ignored. **_now_** The **timestamp** which is used as a base for the calculation of relative dates.
