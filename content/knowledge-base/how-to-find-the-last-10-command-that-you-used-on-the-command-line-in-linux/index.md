---
author: "icarnaghan"
title: "How to find the last 10 command that you used on the command line in Linux"
date: 2018-04-07
---

- Type in the following command in the CLI
    
    ```
    history | tail -n 10
    ```
    
- This command will list the last 10 command line commands that you used.
- Example
    
    ```
      506  history n
    
      507  history | tail 
    
      508  history | tail -10
    
      509  history | tail -n 3
    
      510  pgrep skype
    
      511  pgrep phone
    
      512  grep -rni 'test' *.php
    
      513  cd /var/www/test/
    
      514  grep -rni 'test' *.php
    
      515  history | tail -n 10
    ```
