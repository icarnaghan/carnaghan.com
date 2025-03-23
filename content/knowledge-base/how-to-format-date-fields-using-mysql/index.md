---
author: "icarnaghan"
title: "How to format date fields using MySQL"
date: 2018-03-23
---

Ever wondered how to change the output of the date format using **MySQL**?

If you are constantly logging you're data it's more likely that you will use **DATETIME** fields in a **MySQL** table field to track the dates of events.

What happens if you need to display the date in Human readable format? By using the **DATE\_FORMAT()** function you'll be able to manipulate the Date in almost any possible way.

MySQL Example using the **DATE\_FORMAT()** function:

**DATE\_FORMAT(NOW(),'%W, %M %e, %Y @ %h:%i %p')**  will output **'Sunday, September 20, 2008 @ 12:45 PM'** 

Letter Representations for the **mySql DATE\_FORMAT()** function

| **Specifier** | **Description** |
| :-- | :-- |
| **%a** | Abbreviated weekday name (Sun..Sat) |
| **%b** | Abbreviated month name (Jan..Dec) |
| **%c** | Month, numeric (0..12) |
| **%D** | Day of the month with English suffix (0th, 1st, 2nd, 3rd, …) |
| **%d** | Day of the month, numeric (00..31) |
| **%e** | Day of the month, numeric (0..31) |
| **%f** | Microseconds (000000..999999) |
| **%H** | Hour (00..23) |
| **%h** | Hour (01..12) |
| **%I** | Hour (01..12) |
| **%i** | Minutes, numeric (00..59) |
| **%j** | Day of year (001..366) |
| **%k** | Hour (0..23) |
| **%l** | Hour (1..12) |
| **%M** | Month name (January..December) |
| **%m** | Month, numeric (00..12) |
| **%p** | AM or PM |
| **%r** | Time, 12-hour (hh:mm:ss followed by AM or PM) |
| **%S** | Seconds (00..59) |
| **%s** | Seconds (00..59) |
| **%T** | Time, 24-hour (hh:mm:ss) |
| **%U** | Week (00..53), where Sunday is the first day of the week |
| **%u** | Week (00..53), where Monday is the first day of the week |
| **%V** | Week (01..53), where Sunday is the first day of the week; used with %X |
| **%v** | Week (01..53), where Monday is the first day of the week; used with %x |
| **%W** | Weekday name (Sunday..Saturday) |
| **%w** | Day of the week (0=Sunday..6=Saturday) |
| **%X** | Year for the week where Sunday is the first day of the week, numeric, four digits; used with %V |
| **%x** | Year for the week, where Monday is the first day of the week, numeric, four digits; used with %v |
| **%Y** | Year, numeric, four digits |
| **%y** | Year, numeric (two digits) |
| **%%** | A literal “%” character |
| **%_x_** | _x_, for any “_x_” not listed above |
