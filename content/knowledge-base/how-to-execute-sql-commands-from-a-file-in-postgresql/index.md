---
author: "icarnaghan"
title: "How to execute SQL commands from a file in PostgreSQL"
date: 2018-04-07
---

In my case I had a .sql file with hundreds of insert statements and I wanted to run all of them, I was left with two options namely manually entering every command via copy and paste or executing the file. I went for the second option and it worked. I used Postgres 8.4 on the command line on a Ubuntu machine.

**Answer**:

Follow these steps

- Connect to the relevant database eg.
    
    ```
    sudo -u postgres psql MYDB
    ```
    
- Then run
    
    ```
    \i MYFILEWITHCOMMANDS.sql
    ```
    
    \\i means execute commands from file
- All commands will be executed.
