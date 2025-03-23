---
author: "icarnaghan"
title: "How to create a backup of a PostgreSQL database to a SQL file"
date: 2018-04-07
---

How to create a **backup** of a **PostgreSQL** **database** to a **sql** file? This **sql** file then can be used to **restore** the **database** on a later stage.

Follow the steps below in order to create a backup

1. Open a **Terminal Window** if not yet in **command line**
2. Login as user postgres. **eg. _sudo su postgres_** 
3. Type in the following command pg\_dump db\_name -CdiOv > /tmp/db\_name\_backup.sql
    - **pg\_dump** = Utility to backup a PostgreSQL db.
    - **\-C** = Begin the output with a command to create the database itself and reconnect to the created database.
    - **\-d** = Dump the data as INSERT commands
    - **\-i** \= Ignores version mismatch between the old database server and the new database server.
    - **\-O** = No owner, the database does not belong to any specific owner that was specified in the database
    - **\-v** \= Verbose, will output a detailed report of pg\_dump if ran in command line.
    - **\> /tmp/db\_name\_backup.sql** = dump the output of the command into a file called **db\_name\_backup.sql** (Here you may choose any location on your drive where you want the backup to be stored)
4. Now you have a **backup** of your **pqsl** **database** in **sql** file format

**NOTE**: PostgreSQL 8.3.7 has been used and installed on Ubuntu 9.04 with this how-to
