---
author: "icarnaghan"
title: "Calculating the difference in days between 2 dates in PHP"
date: 2018-03-22
---

```
$startDate = '1999-03-12';
 
$endDate = '2011-03-12';
 
 
$days = (strtotime($endDate)-strtotime($startDate)) / (60 * 60 * 24);
 
echo $days; //Will output 4383
```

In the above example we have a **startdate** and a **enddate**. We need to find out how many **days** are **between** the **startdate** and the **enddate**.

We convert both **dates** to a **UNIX Timestamp** using the _**strtotime**_ **PHP function**.

After the **conversion** we **substract** the **startdate** from the **endate** and then **divide** it by the **number of seconds in a day (60\*60\*24).**

We then **output** the **day** **difference** **between** 2 dates by using the _**echo**_ **PHP command**.
