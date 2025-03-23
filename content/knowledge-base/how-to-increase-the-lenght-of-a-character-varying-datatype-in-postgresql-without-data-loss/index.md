---
author: "icarnaghan"
title: "How to increase the lenght of a character varying datatype in PostgreSQL without data loss"
date: 2018-04-07
---

Run the following command

```
alter table TABLE_NAME alter column COLUMN_NAME type character varying(120);
```

This will extend the **character varying** column **field** **size** to **120**.

Remember to change **TABLE\_NAME** to the relevant table name and **COLUMN\_NAME** to the relevant **column name**.
