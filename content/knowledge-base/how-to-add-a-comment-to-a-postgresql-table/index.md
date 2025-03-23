---
author: "icarnaghan"
title: "How to add a comment to a PostgreSQL table"
date: 2018-04-07
---

If you have a table with the name **transactions** and you need to add a comment to this table for future references you can add a comment by using the code below, replacing the table name and the comment to suite your needs.

```
COMMENT ON TABLE "transaction" IS 'This table keeps a log of all orders that went through the website';
```
