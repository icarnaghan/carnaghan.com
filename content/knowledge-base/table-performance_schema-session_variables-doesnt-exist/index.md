---
author: "icarnaghan"
title: "Table 'performance_schema.session_variables' doesn't exist"
date: 2018-03-23
---

**Solution 1**

Upgrade your MySql server. After the upgrade reboot the server

```
mysql_upgrade -u root -p --force
systemctl restart mysqld
```

**Solution 2

**This solution is not permanent. After the next reboot of the MySql server all changes will be lost.

```
mysql -u app -p
mysql> set @@global.show_compatibility_56=ON;
```

**Solution 3**

This solution is permanent. Locate and edit your MySql config file: **my.cnf**

Under the \[mysqld\] config section add the following line:

```
show_compatibility_56 = ON
```

Sample:

```
[mysqld]
port = 3306
show_compatibility_56 = ON
performance_schema=ON
```

Restart your MySql Server

**NOTES:

**show\_compatibility\_56 is deprecated because its only purpose is to permit control over deprecated system and status variable information sources that will be removed in a future MySQL release. When those sources are removed, show\_compatibility\_56 will have no purpose and will be removed as well.

**Reference**: https://dev.mysql.com/doc/refman/5.7/en/server-system-variables.html#sysvar\_show\_compatibility\_56
