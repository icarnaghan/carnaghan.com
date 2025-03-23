---
author: "icarnaghan"
title: "How to import a generated MySQL file '.sql' via the CLI (Command Line Interface)"
date: 2018-03-23
---

- Open a new **Terminal Window** if not already in **Command Line**
- Type in the command below
    - **Linux**
        
        ```
        mysql -uusername -ppassword databasename < import.sql
        ```
        
    - **Windows**
        
        ```
        mysql -u username -p databasename < import.sql
        ```
