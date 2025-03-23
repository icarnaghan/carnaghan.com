---
author: "icarnaghan"
title: "How to check the encoding for a database in PostgreSQL"
date: 2018-04-07
---

To do this **login** to the **command line** and **switch** to the main **Postgres** **user**. eg _**su postgres**_

The type the **psql -l** command this will produce a **list of databases** with there **encodings**

```
 
	                List of databases
 
	          Name          |   Owner    | Encoding  
 
	------------------------+------------+-----------
 
	 DB1                    | postgres   | UTF8
 
	 DB2                    | postgres   | UTF8
 
	 DB3                    | postgres   | UTF8
 
	 DB4                    | clicks     | SQL_ASCII
 
	 DB5                    | clicks     | SQL_ASCII
```
