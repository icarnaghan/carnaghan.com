---
author: "icarnaghan"
title: "How to convert a MySQL Datetime field to a Unix Timestamp using PHP"
date: 2018-03-22
---

In the example you'll find a handy PHP function that will do the conversion.

```
<?php 
 
$DATETIME = '2010-04-22 19:54:38';
 
echo convertDateTime($DATETIME);
 
/*
 * This function converts a mysql datetime to a unix timestamp
 * The format should be "YYYY-MM-DD HH:MM:SS"
 *
 * @param $datetime string Contains the DATETIME value
 * @return UNIX TIMESTAMP
 */
function convertDateTime($datetime) {
    list($date, $time) = explode(' ', $datetime);
    list($year, $month, $day) = explode('-', $date);
    list($hours, $minutes, $seconds) = explode(':', $time);
    
    $UnixTimestamp = mktime($hours, $minutes, $seconds, $month, $day, $year);
    return $UnixTimestamp;
}
 
?>
```

First we divide the date from the time and then break up the date into year, month and day variables. After that we break the time up into hour, minute and second and then we create a Unix Timestamp using the **mktime** PHP function.
