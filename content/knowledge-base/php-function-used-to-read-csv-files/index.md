---
author: "icarnaghan"
title: "PHP function used to read CSV files"
date: 2018-03-22
---

The below function can be used to read CSV files and returning an array with all values obtained from the CSV file

**USAGE:**

Copy the below function to your PHP script

```
function readCSV($csvFile){
 
 
        $file_handle = fopen($csvFile, 'r');
 
        while (!feof($file_handle) ) {
 
                $line_of_text[] = fgetcsv($file_handle, 1024);
 
        }
```
