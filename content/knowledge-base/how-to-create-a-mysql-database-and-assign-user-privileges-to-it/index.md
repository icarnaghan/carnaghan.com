---
author: "icarnaghan"
title: "How-to create a MySQL database and assign user privileges to it"
date: 2018-03-23
---

**NOTE**: Please note that this is done in the Command Line Interface.

- First login to the mySql server using root.
    
    ```
    mysql -uroot -pROOT_PASSWORD
    ```
    
    Replace ROOT\_PASSWORD with the password for the root user.
- Once logged in we create a new database called TEST\_DB replace with your database name
    
    ```
    create database TESTDB;
    Query OK, 1 row affected (0.00 sec)
    ```
    
- We grant access privileges to user MYUSER to connect to the mysql server from localhost using the password MYPASSWORD
    
    ```
    grant usage on *.* to MYUSER@localhost identified by 'MYPASSWORD';
    Query OK, 0 rows affected (0.00 sec)
    ```
    
- Now we grant all privileges to MYUSER on the database TESTDB
    
    ```
    grant all privileges on TESTDB.* to MYUSER@localhost ;
    Query OK, 0 rows affected (0.00 sec)
    ```
    
- Type exit to log out
    
    ```
    exit;
    ```
    
- Now you can login to TESTDB using user MYUSER and password MYPASSWORD
    
    ```
    mysql -u MYUSER -p'MYPASSWORD' TESTDB
    ```
