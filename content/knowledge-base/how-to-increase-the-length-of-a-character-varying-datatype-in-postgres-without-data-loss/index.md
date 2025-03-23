---
author: "icarnaghan"
title: "How to increase the length of a character varying datatype in Postgres without data loss"
date: 2018-09-02
---

Run the following command:

```
alter table TABLE_NAME alter column COLUMN_NAME type character varying(120);
```

This will extend the **character varying** column **field** **size** to **120**.

Remember to change **TABLE\_NAME** to the relevant table name and **COLUMN\_NAME** to the relevant **column name**.
