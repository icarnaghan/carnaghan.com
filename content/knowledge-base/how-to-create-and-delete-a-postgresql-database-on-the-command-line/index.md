---
author: "icarnaghan"
title: "How to create and delete a PostgreSQL database on the command line"
date: 2018-04-07
---

This can be accomplished by using the **dropdb** and **createdb** command line wrappers

The syntax to **create** a new **database** on the command line is createdb _**\[ options \] dbname**_

 

**Example**:

```
createdb -O user  new_database - E UTF8
```

This will create a new database called **new\_database** and assign the user **user** to it and use the encoding **UTF8**

 

To **drop** a **database** on the command line the syntax **_dropdb \[ options \] dbname_** is used.

 

**Example:**

```
dropdb new_database
```
