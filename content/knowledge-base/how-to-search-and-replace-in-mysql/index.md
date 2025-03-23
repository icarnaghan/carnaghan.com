---
author: "icarnaghan"
title: "How to search and replace in MySql"
date: 2018-03-23
---

The code below will do the trick, this line can be modified to accomodate your needs. A **where** clause can also be added

```
UPDATE databaseTableName SET tableColumnName = replace(tableColumnName,"findValue","replaceValue");
```
