---
author: "icarnaghan"
title: "How to validate a date format using PHP"
date: 2018-03-22
---

To check whether the date entered is in the correct format

**NOTE**: We will use the following date format within this example _YYYY-MM-DD_

**Answer**:

- Use the **preg\_match** _'Perform a regular expression match'_  PHP function available for _PHP 4 & 5_ 
- Find the correct expression
- And use the following code to check for the date format
    
    ```
    if(preg_match('/[12]\d{3}-[01]\d-[0123]\d/',$date)){
        $msg = "Valid date";
    }else{
        $msg = "Invalid date";
    }
    ```
