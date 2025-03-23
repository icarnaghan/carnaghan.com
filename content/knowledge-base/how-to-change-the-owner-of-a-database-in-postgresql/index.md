---
author: "icarnaghan"
title: "How to change the owner of a Database in PostgreSQL"
date: 2018-04-07
---

First you need to login with the Super User e.g.

```
psql postgres
```

After logged-in type the following command

```
ALTER DATABASE database OWNER TO newuser;
```

Replace **database** with your database and **newuser** with your username
