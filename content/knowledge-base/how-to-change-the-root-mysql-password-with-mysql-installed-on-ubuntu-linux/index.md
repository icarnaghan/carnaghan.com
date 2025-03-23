---
author: "icarnaghan"
title: "How to change the root MySQL password with MySQL installed on Ubuntu/Linux"
date: 2018-04-07
---

1. Open a new **Terminal Window**.
2. Type in the commands below.
    
    ```
     mysqladmin
    ```
    
    ```
     -u root OLDPASSWORD NEWPASSWORD
    ```
    
3. If you get the error below follow **solution 2**
    
    ```
     mysqladmin: connect to server at 'localhost' failed
    
     error: 'Access denied for user 'root'@'localhost' (using password: YES)'
    ```
    
4. If you did not get the error above restart the **mySql** server by typing the following command:
    
    ```
    sudo service mysql restart
    ```
    

**Solution 2**:

1. If **Solution 1** did not work, this should work.
2. **mySql** stores **usernames** together with their **passwords** in the **user table** in the **mySql** database.
3. Open a new **Terminal Window** and type in the command below to Login to the **mySql server**.
    
    ```
    mysql -u root -p
    ```
    
4. Enter your **password**.
5. Now you need to switch to the mysql database. Type the command below
    
    ```
    mysql> use mysql;
    ```
    
6. Now we need to change the **password**. Type in the following command:
    
    ```
    mysql> update user set password=PASSWORD("NEW_PASSWORD") where User='USERNAME';
    ```
    
7. Flush the privileges (Reloading them) using command below:
    
    ```
    mysql> flush privileges;
    ```
    
8. ```
    Exit mySql
    mysql>quit
    ```
