---
author: "icarnaghan"
title: "How to Export your MySQL database schema to a file using the Command Line"
date: 2018-03-23
---

Use the following command in the **Command Line Interface**

```
mysqldump --no-data --tables -uMYSQL_USER_NAME -pMYSQL_PASSWORD MYSQLDATABASE >> FILE_NAME.sql
```

Replace **MYSQL\_USER\_NAME** with your username,  **MYSQL\_PASSWORD** with your password, **MYSQLDATABASE** with the database name you want to export and**FILE\_NAME.sql** with the file that you wish to export the schema to.
