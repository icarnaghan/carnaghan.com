---
author: "icarnaghan"
title: "How to view the character set and collation on a database in MySql"
date: 2018-03-23
---

Select your database via the command line:

```
USE your_database;
```

Then execute the following two commands:

```
show variables like "character_set_database";
```

and

```
show variables like "collation_database";
```
