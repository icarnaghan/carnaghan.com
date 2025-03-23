---
author: "icarnaghan"
title: "How to delete a column in a database table using PostgreSQL via the command line"
date: 2018-04-07
---

Use the following statement

```
ALTER TABLE my_table DROP COLUMN my_column;
```

Replace **my\_table** with the your table name and **my\_column** with the column that you need to drop/remove.
