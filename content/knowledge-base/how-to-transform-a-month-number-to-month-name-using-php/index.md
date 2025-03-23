---
author: "icarnaghan"
title: "How to transform a month number to month name using PHP"
date: 2018-03-22
---

```
$month = 1;
 
$month_name = date("F", mktime(0,0,0,$month,1,2011));
 
echo $month_name; //Will output January
```
