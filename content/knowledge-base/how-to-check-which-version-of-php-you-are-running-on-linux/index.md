---
author: "icarnaghan"
title: "How to check which version of PHP you are running on Linux"
date: 2018-03-22
---

**NOTE**: Tested on Centos 4 & 5 and Ubuntu 9.04

- In the command line type in the following command to get all **PHP information and configurations**
    
    ```
    php -i
    ```
    
- To get the Version number use the following command
    
    ```
    php -v
    ```
    
- Or this command:
    
    ```
    php -i | grep 'PHP Version'
    ```
