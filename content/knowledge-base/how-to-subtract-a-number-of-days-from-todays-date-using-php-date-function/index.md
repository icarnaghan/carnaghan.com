---
author: "icarnaghan"
title: "How to subtract a number of days from todays date using PHP date function"
date: 2018-03-22
---

$var = '2007-08-15'; $var\_subtracted\_date = **date**('Y-m-d', **strtotime**('-2 days', **strtotime**($var)));

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

**EXAMPLE**

echo **strtotime**("now"), "\\n"; echo **strtotime**("10 September 2000"), "\\n"; echo **strtotime**("+1 day"), "\\n"; echo **strtotime**("+1 week"), "\\n"; echo **strtotime**("+1 week 2 days 4 hours 2 seconds"), "\\n"; echo **strtotime**("next Thursday"), "\\n"; echo **strtotime**("last Monday"), "\\n";
