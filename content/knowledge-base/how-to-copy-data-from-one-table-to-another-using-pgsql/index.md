---
author: "icarnaghan"
title: "How to copy data from one table to another using pgsql"
date: 2018-04-07
---

If you need to copy data from one table (table\_a) into another table (table\_b) using pgsql.

There are 2 methods on how to do this.

**Method 1**

NOTE: _If you are using this method table\_b should not yet exist._

If you want an exact duplicate without indexing or relying on objects use this.

**SELECT \* INTO table\_b FROM table\_a**

**Method 2**

NOTE: _This method will work if table\_b already exist._

This method uses a subselect inside the INSERT statement

**INSERT INTO table\_b ( SELECT \* FROM table\_a WHERE condition );**
