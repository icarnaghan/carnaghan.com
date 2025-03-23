---
author: "icarnaghan"
title: "How to remove all characters exept numbers from a string using PHP"
date: 2018-03-22
---

This is really easy, we will make use of the **_preg\_replace_** **PHP** **Function** which is 100% compatible with **PHP 5.3**

**Example:** 

```
$string = 'This is my phone number: +28 (0)212 1234!!! '
 
$numberString = preg_replace('[\D]', '', $string);
 
echo $numberString; //Will output 2802121234
```

This is a good way to format phone numbers etc.

The regular expression character **\\D** means to match a character that's not a digit
