---
author: "icarnaghan"
title: "How to remove values in one array from another array using PHP"
date: 2018-03-22
---

**Example**: I have array **A** with values and another array **B**. I need to remove the values in array **A** from the values in array **B**.

 

1. Use the PHP function **array\_diff**
    
    - **Description**
        - array **array\_diff** ( array $array1 , array $array2 \[, array $ ... \] )
        - Compares array1  against array2  and returns the difference.
    
    - **Parameters**
        - array1 = The array to compare from
        - array2 = An array to compare against
2. Code example below:
    
    ```
    <?php
    
        $arrayA = array('one','two');
    
        $arrayB = array('one','two','three','four','five');
    
        
    
        $newArray = array_diff($arrayB,$arrayA);
    
        
    
        echo '<pre>';
    
        print_r($newArray);
    
        echo '</pre>';
    
    ?>
    ```
    
3. The code example above will print the following:
    
    ```
    Array
    
    (
    
        [2] => three
    
        [3] => four
    
        [4] => five
    
    )
    ```
    
4. Explanation:
    - Array **A** values will be removed from array **B**
    - The **$newArray** variable will contain the values of array **B** with values from array **A** removed
