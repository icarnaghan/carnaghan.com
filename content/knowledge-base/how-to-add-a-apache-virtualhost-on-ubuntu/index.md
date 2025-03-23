---
author: "icarnaghan"
title: "How to add a Apache VirtualHost on Ubuntu"
date: 2018-04-07
---

With this tutorial I assume that you know what **Apache web server** is and that you have **PHP** and **Apache** installed on your machine. Also ensure that you are able to serve web pages.

**NOTE**: This has been tested on **Ubuntu 9.04**

 

**Answer**:

1. Open your **Terminal Window** or the **command line**.
2. Navigate to the **/etc/apache2/sites-available** directory with this command: cd /etc/apache2/sites-available
3. Create a **new file** in this **directory** called **sitename.conf** or anything you would like to call your new **VirtualHost**. Use the following command: sudo gedit sitename.conf
4. Add the following code in the **sitename.conf** file
    
    _**<VirtualHost \*:80> ServerAdmin yourname@domain.com ServerName  sitename ServerAlias** **sitename**       **DocumentRoot /var/www/****sitename****/ <Directory /var/www/****sitename****/> Options FollowSymLinks AllowOverride All Order allow,deny allow from all </Directory> </VirtualHost>
    
    **_
5. Save file and exit.
6. Open the **/etc/hosts** file with command: sudo gedit /etc/hosts 
7. Add the following code to it _**127.0.0.1 localhost sitename**_
8. Save file and exit
9. **Enable** your new **VirtualHost**  Use this command: sudo a2ensite sitename.conf
    - Creates a symbolic link to **/etc/apache2/sites-enabled**
    - In the **/etc/apache2/apache2.conf** file it includes the **/etc/apache2/sites-enabled directory** to include the **virtual host configurations**, so all **VirtualHosts** will be included everytime **Apache** starts.
10. Restart **Apache** with command: sudo /etc/init.d/apache2 restart or sudo service apache2 restart
11. Now  your new **VirtualHost** should be enabled!
