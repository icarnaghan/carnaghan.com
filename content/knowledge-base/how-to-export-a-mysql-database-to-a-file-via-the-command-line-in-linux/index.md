---
author: "icarnaghan"
title: "How to export a MySql database to a file via the Command Line in Linux"
date: 2018-03-23
---

- Open a new **Terminal Window**
- Type in the following command {codecitation class="brush: bash;"} mysqldump -uUsername -pPassword DatabaseName \> outputFile.sql {/codecitation}
- The command above will export a selected database to a file called **outputFile.sql**
    - **mysqldump** = _a database backup program_
    - **\-u** = _Username for the database_
    - **\-p** \= _Password for the database_
    - **DatabaseName** \= _The database name you wish to export_
