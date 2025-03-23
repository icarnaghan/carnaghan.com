---
author: "icarnaghan"
title: "ERROR 1194 (HY000): Table 'mytable' is marked as crashed and should be repaired, how do I fix this?"
date: 2018-03-23
---

**Error: 1194 SQLSTATE: HY000**: means **ER\_CRASHED\_ON\_USAGE**

In the **mySql command line** you should run the following command to **repair** the table

```
repair table mytable;
```

//Replace mytable with your table name

**REPAIR TABLE**  repairs a possibly corrupted table. To read more about the **REPAIR TABLE** command click here.

**NOTE**: If you do not have access to the command line then **phpMyAdmin** should have a repair table option.
