---
author: "icarnaghan"
title: "How to output my MySql query results to a CSV file on the command line"
date: 2018-03-23
---

Type in the following command

```
SELECT id,clientid,company FROM config INTO OUTFILE '/tmp/List.csv' FIELDS TERMINATED BY ',' LINES TERMINATED BY '\n';
```

The command above will **output** the **results** from the **MySql query** into a **Comma Separated File** called **List.csv**, it will split the **columns** by using a **comma ","** and will **terminate** every **new line** with the **line break character** **\\n**
