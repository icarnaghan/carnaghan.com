---
author: "icarnaghan"
title: "Getting errors when running Joomla! 1.7 and 1.6 in XAMPP on Localhost"
date: 2018-03-25
---

The error messages that I get are all **Strict Standards: Accessing static property JCache::$\_handler as non static** which is causing an annoying working experience with **Joomla!**

**Answer**:

1. Locate your **php.ini** file in **_c:\\xampp\\php\\php.ini_**
2. _L_ocate **_error\_reporting =_**  and change the value to _**error\_reporting = E\_ALL & ~E\_NOTICE & ~E\_DEPRECATED**_
3. Locate locate _**display\_errors = On**_ and change the value to _**display\_errors = Off**_
4. Stop and restart **Xampp** and the problem will be gone

If the above did not solve your problem visit the following topic on the Joomla! forums by clicking here
