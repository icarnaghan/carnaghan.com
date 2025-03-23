---
author: "icarnaghan"
title: "How to change the root password for MySql under Linux in the command line"
date: 2018-03-23
---

You will need to know the current **root password** in order to change it

In the command line type in and execute the following command

```
mysqladmin -u root -pOLD_PASSWORD password NEW_PASSWORD
```

Replace **OLD\_PASSWORD** with your old password and **NEW\_PASSWORD** with your new password.
