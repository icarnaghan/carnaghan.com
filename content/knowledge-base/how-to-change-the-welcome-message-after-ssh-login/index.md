---
author: "icarnaghan"
title: "How to change the welcome message after SSH login"
date: 2018-04-07
---

1. Login as root via SSH
2. Add a message to /etc/motd using vim eg.
    
    ```
    vim /etc/motd
    ```
    
3. Add your message to this file eg.
    
    ```
    ###Please think before you type###
    ```
    
4. Logout
5. Login via SSH and then after successful login the message will appear
