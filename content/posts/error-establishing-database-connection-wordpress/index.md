---
author: "prhost78"
title: "Fix Error Establishing a Database Connection in WordPress"
date: 2016-04-24
categories: 
  - "cms"
tags: 
  - "affiliate"
  - "database"
  - "wordpress"
  - "wordpress-plugins"
---

WordPress saves the post, settings and other data related to your website in an MSQL database. The DB is handled by the user through CMS with a DB management plugin or through a command line terminal from a remote computer (on unmanaged hosting environment).

Sometimes, the WordPress PHP files will not be able to connect to the MySQL server, and you'll be notified of this error when you try to access any page of your website.  Today, we'll share some effective tips to fix this common WordPress problem and avoid it in the future.

### When do you see the error establishing database connection error?

#### Incorrect details in the wp-config file

WP config file is one of the most important files in the WordPress setup. It stores the username DB name, host, and password for allowing the theme and WordPress core files to access the MySQL DB

If any of these four details is incorrect, the theme or the CMS will not be able to connect to the DB server due to which you'll see the error establishing the database connection error.

To fix this problem, check whether the username you have entered is correct or not. If the username is right, check if it has been assigned the required privileges or not.

If this doesn't help, make sure that you've entered the correct DB name in the wp-config file. Fire the SHOW DATABASES MySQL query in the shell or use CPANEL to check the list of databases you've created.

If the DB name has been specified correctly, check if the password you've entered in the wp-config is valid or not. If you've mistakenly entered the password incorrectly, rectify it.

![fix error establishing a database connection error in WordPress](images/db-connection-error.jpeg)

 

#### MySQL doesn't start when you restart the OS

This is a common problem that webmasters face when they host their websites on an unmanaged VPS. After upgrading the server software, you might have to reboot the server to begin using the latest software.

You may not have configured the MySQL service to start automatically when the OS reboots. In such situation, your WordPress database will not be accessible by the WordPress files when you restart the VPS.

To fix this problem, fire the below two commands in the terminal (after establishing SSH connection with your VPS server).

`sudo service mysqld start sudo chkconfig --level 2345 mysqld on`

The 1st command will start MYSQL, and the 2nd command will modify system configuration to start the MYSQL service when the server restarts.

#### Missing DB table or problem reading the database

A malicious code might have removed big tables from the DB and the PHP file depending on it is not able to find the required tables. In such cases, restore the database backup and restart MySQL.

#### High traffic

A high traffic website hosted on a low-end server might report several issues. If the database is not able to handle the requests, it might crash. To get rid of this problem, host your high traffic website on a powerful VPS, enable Opcode, Nginx caching as well as MYSQL Query caching.

**Conclusion**:

You'll see the error establishing database connection only in one of the situations mentioned above. Make sure that you follow the tips we've shared to fix the issue and avoid it in the future.
