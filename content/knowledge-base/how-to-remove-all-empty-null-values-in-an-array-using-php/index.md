---
author: "icarnaghan"
title: "How to remove all empty/null values in an array using PHP"
date: 2018-03-22
---

1. If you have an **array** with empty values and you wish to **remove** the **empty** **values**you can use the following one line code
    
    ```
    		$array = array('','1','','3');
     
    		$array = array_filter($array, 'strlen');
     
     
     
    		echo '<pre>';
     
    		print_r($array);
     
    		echo '</pre>';
    
    ```
    
2. The result will be only the **NOT NULL values**
    
    ```
    Array
    (
        [1] => 1
        [3] => 3
    )
    ```
