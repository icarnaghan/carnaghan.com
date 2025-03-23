---
author: "icarnaghan"
title: "Error: \"Ignoring query to other database\" when running a mySql command in the command line"
date: 2018-03-23
---

E.g. **SELECT  \* FROM users;** or **SHOW tables;**

In the command line make sure you used the correct syntax when connecting to mySql

**Correct example:**

```
mysql -uroot -ppassword
```

**Wrong example:** _(This is what I did that caused this error)_

```
mysql -rroot -ppassword
```
