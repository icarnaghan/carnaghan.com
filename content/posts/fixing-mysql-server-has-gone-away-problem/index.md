---
author: "prhost78"
title: "Fixing MySQL Server Has Gone Away problem"
date: 2016-05-13
categories: 
  - "coding"
tags: 
  - "affiliate"
  - "database"
  - "mysql"
---

All my websites are hosted on an unmanaged VPS. The VPS has enough of RAM and a decent CPU. It can handle ten high traffic blogs.

I had never faced any problems until last week when my website started displaying error establishing a database connection to the visitors instead of the content. This error was reported after I changed one of the table's structure.

#### Why the heck did I change the structure?

Last week, I noticed Yarpp plugin displayed a message that I need to replace the table structure of my post content table from INNODB to MYISAM so that the plugin can display highly relevant related posts. So I changed the structure of my website's DB table.

![Fixing mysql server has gone away problem](images/mysql-d.jpg)

To fix the problem, I started MySQL service. Unfortunately, this was not a permanent solution. After a few hours, the WordPress front end was not able to connect to the DB.

I checked the logs and found that the MYSQL server was unable to process the WordPress theme and plugin queries. The log file was populated with MYSQL server has gone away messages. I followed the below methods to get things back on track:

### Repair MySQL DB

The mysqld.log file in /var/logs folder displayed the 'performance\_schema' has the wrong structure error. I disabled full text indexes created by WordPress Yarrp plugin from the MyISAM table and changed it structures back to INNODB. After this, I ran the below command in the terminal.

`mysql_upgrade -u root -p`

The above command will find faults in the DB tables structure, and it will repair them.

### Enable Query cache

Enabling the query cache will reduce the load of the database significantly. You can do this by adding query\_cache\_size variable in my.cnf file located under the /etc directory. This module also improves the website's performance as data is fetched from the cached results.

### Change Max connections limit of MySQL

When you install a lot of plugins, the performance of your site will decrease, and system resource usage will increase. The plugins may require a higher volume of RAM to complete its job.

If the code's RAM/CPU requirements don't meet, the plugin may not work. A poorly designed plugin may fire 100s of queries at a time.

Such plugins can have a negative impact on a DB server. EX: MySQL has been configured to handle max 50 connections. A bad code/plugin attempts to create 1000 connections with MYSQL. In such cases, the Mysql server may crash.

MySQL server can handle any number of requests. You should configure it as per the website's requirement with the max\_connections variable. Visit this page of the official MYSQL website for more information on the same.

### Change max execution time in PHP.ini

Sometimes, a PHP code might take more time to execute a task. If the PHP code stops the middle way of execution, your site may crash. To avoid this scenario, always set the maximum execution time for 60 or more. The variable for the same (max\_execution\_time) can be found in the PHP.ini file.

### Create CronJob for restarting MYSQL automatically

Crontab is one of the most useful tools in Linux OS. With it, the user can schedule tasks. They can configure crontab to run shell scripts, programs, etc. If the above methods don't work for you, then create a cronjob for restarting MYSQL server automatically when it stops unexpectedly.

To do this, write a shell script that checks MySQL status. If the status is stopped, the script should be able to run the MySQL server. Make sure that the cronjob is configured to execute every 2 to 5 minutes. Please refer this answer on askubuntu portal from Radu Rădeanu to learn how to create such script and cron job.

**Conclusion**: The MySQL server has gone away is a tricky problem. If you've encountered this error, follow the methods we've shared above to fix it.
