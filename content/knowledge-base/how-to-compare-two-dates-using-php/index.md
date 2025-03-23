---
author: "icarnaghan"
title: "How to compare two dates using PHP"
date: 2018-03-22
---

- First we need to convert the two dates to **UNIX Timestamps** using the PHP function _**strtotime**_
- Then we can compare the two dates in anyway we wish, in the example below I'm checking that the _**first date is older than the second date**_ 
    
    ```
    $date1 = '1999-10-11';
    $date2 = '2010-10-11';
     
    $firstDate = strtotime($date1);
    $secondDate = strtotime($date2);
     
    if($firstDate < $secondDate){
         echo 'First date is older';
    }else{
         echo 'Second date is older';
    }
    ```
