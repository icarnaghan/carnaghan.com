---
author: "icarnaghan"
title: "How to use the CONCAT MySql function to concatenate 2 table columns"
date: 2018-03-23
---

The **CONCAT** function can be used to concatenate two strings to form a single string or two columns to form a single column.

Say for Example you have a table **users** with columns **name** and **surname** and you would like to display both as one name you would use the **CONCAT** function to join the two fields as in the Example below

```
SELECT CONCAT(name," ",surname) AS fullname FROM users;
```

The above code will display something similar to _**Joe Soap**_ should Joe be stored in the name column and Soap be stored in the surname column.
