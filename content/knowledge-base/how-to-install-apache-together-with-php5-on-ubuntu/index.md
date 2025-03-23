---
author: "icarnaghan"
title: "How to install Apache together with PHP5 on Ubuntu"
date: 2018-04-07
---

How to install **Apache** together with **PHP5** on **Ubuntu**? This becomes very handy if you wish to do some **PHP** development on **Ubuntu**.

 

1. Open a new **terminal window (CLI)**
2. Execute the following commands:
    
    ```
    sudo apt-get install apache2
    sudo apt-get install php5
    sudo apt-get install libapache2-mod-php5
    
    ```
    
3. Now we need to restart **Apache** so that our changes can take effect. There are two commands for you to choose from
    
    ```
    sudo /etc/init.d/apache2 restart
    ```
    
    or
    
    ```
    sudo service apache2 restart
    ```
