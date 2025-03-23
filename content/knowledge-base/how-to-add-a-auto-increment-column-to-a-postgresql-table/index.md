---
author: "icarnaghan"
title: "How to add a Auto Increment Column to a PostgreSQL table"
date: 2018-04-07
---

Unfortunately **Postgresql** does not have **Auto Increment columns** so instead we create a **Sequence** that will act as a **counter**

First we'll need to create a sequence that we want to attch to our table

```
CREATE SEQUENCE mytable_primary_id_seq;
```

Then we need to assign the sequence to the column in our table that will act as the Autoincrement column

```
ALTER TABLE mytable
	    ALTER COLUMN primary_id
	        SET DEFAULT NEXTVAL('mytable_primary_id_seq');
```

No we need to fill in an **auto increment value** for all **records** that **existed** in the **table**before we added a **sequence** to the **table** column **primary\_id**

```
UPDATE mytable
	    SET primary_id = NEXTVAL('mytable_primary_id_seq');
```
