---
author: "icarnaghan"
title: "How to drop a entire MySql Database on the command line in Linux"
date: 2018-03-23
---

Login to the MySql command line using something like the following

```
mysql -uUSERNAME -pPASSWORD
```

Then execute the following command to Drop the desired Database

```
DROP TABLE MYDATABASE;
```

Replace **MYDATABASE** with the **Database** **name** that you want to **Drop**

**Note**: Please note that this can't be undone, so please create a backup before proceeding.
