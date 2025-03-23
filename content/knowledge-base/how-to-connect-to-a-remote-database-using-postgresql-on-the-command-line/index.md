---
author: "icarnaghan"
title: "How to connect to a remote database using PostgreSQL on the command line"
date: 2018-04-07
---

On the command line type in the following command

```
psql -h 196.41.214.143 -U USERNAME -d DATABASE
```

Replace **USERNAME** with the username associated to the database and **DATABASE**with the database name.

After executing the command it will prompt you for you password
