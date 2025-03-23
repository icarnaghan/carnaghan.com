---
author: "icarnaghan"
title: "How to send the output of a PostgreSQL query to a CSV file using the CLI (Command Line Interface)"
date: 2018-04-07
---

- Log into the PostgreSQL interface on the command line, you should see a similar screen like the one below
    
    ```
    Welcome to psql 8.1.21, the PostgreSQL interactive terminal.
     
    Type:  \copyright for distribution terms
           \h for help with SQL commands
           \? for help with psql commands
           \g or terminate with semicolon to execute query
           \q to quit
     
    database=# 
    
    ```
    
- Type the following command
    
    ```
    \o /tmp/output.csv
    ```
    
    - Make sure the Postgres user has write privileges to the directory specified
    - **/tmp/output.csv** is the directory and the csv file name
    - **\\o** \= Put all query output into file **output.csv**
- Run your sql query eg.
    
    ```
    SELECT * FROM users;
    ```
    
- Type **\\q** to quit the PostgresSQL interface
- Browse to the **/tmp/** directory
- Open the **output.csv** file and all the data from the users table will be within this CSV file, and the columns will be comma seperated.
