---
author: "icarnaghan"
title: "Calculating the date difference in days using PHP"
date: 2018-03-22
---

If you have 2 dates and you need to calculate the total days between these two dates using PHP you will need to do the following

First, we need to convert the two dates into UNIX timestamps in seconds

```
$date1 = strtotime('2010-10-12');
$date2 = strtotime('2011-11-12');
```

Calculate the difference between these two dates in seconds

```
$diff = $date2-$date1;
```

Get the total of Days

```
$days = floor($diff/(60*60*24));
```

The **floor** function is there to get complete days. **60\*60\*24** means that each day has 24 hours, each hour has 60 minutes and each minute has 60 seconds.

Complete example

```
$date1 = strtotime('2010-10-12');
$date2 = strtotime('2011-11-12');
 
$diff = $date2-$date1; 
 
$days = floor($diff/(60*60*24));
```
