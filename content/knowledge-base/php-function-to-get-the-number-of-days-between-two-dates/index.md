---
author: "icarnaghan"
title: "PHP function to get the number of days between two dates"
date: 2018-03-22
---

The below function can be used to calculate the difference in days between two dates

**USAGE:**

```
/**
 * Getting the number of days between two dates
 * 
 * @param string $date1 yyyy-mm-dd
 * @param string $date2 yyyy-mm-dd
 * @return integer
 */
function getDiffInDays($date1,$date2){
     $datediff = strtotime($date1)-  strtotime($date2);
     return floor($datediff/(60*60*24));
}
```

```
$days = getDiffInDays('2013-02-15','2013-01-26');
```
