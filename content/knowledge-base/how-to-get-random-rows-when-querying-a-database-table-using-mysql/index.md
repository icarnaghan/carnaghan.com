---
author: "icarnaghan"
title: "How to get random rows when querying a database table using MySQL"
date: 2018-03-23
---

For example, if you have a table with 100 rows in it and you need to get 3 random rows then this could come in handy. 

```
SELECT * FROM ads ORDER BY RAND() LIMIT 3
```

We've used the RAND() function to return random table rows
