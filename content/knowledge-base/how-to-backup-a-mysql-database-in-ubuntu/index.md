---
author: "icarnaghan"
title: "How to backup a MySQL database in Ubuntu"
date: 2018-03-23
---

1. Open a new **Terminal Window**.
2. Type in the following **command**: mysqldump -h localhost -u root -pPASSWORD database > backup.sql
3. This will **backup** the database to the file **backup.sql**
4. \-h = _Hostname_ -u = _Username_ -p = _Password, no space between the p and the password allowed_

**NOTE**: Has been tested on Ubuntu 9.04 and mySql 5.0.75
