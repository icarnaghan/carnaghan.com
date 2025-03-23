---
author: "icarnaghan"
title: "How to get the last character in a string using PHP"
date: 2018-03-22
---

- This can be done by using the substr which will return a part of a string.
- The sample code below will return the letter **f**
    
    ```
    $lastChar= substr("abcdef", -1);
    ```
    
    The -1 is negative, the returned string will start at the last character from the end of the string.
