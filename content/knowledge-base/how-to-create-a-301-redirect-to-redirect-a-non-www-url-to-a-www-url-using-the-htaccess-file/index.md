---
author: "icarnaghan"
title: "How to create a 301 redirect to redirect a non www URL to a www URL using the .htaccess file"
date: 2018-03-22
---

1. Create a **.htaccess** file within your web directory where all your website files are located
2. Add the following code to it
    
    ```
    RewriteEngine On
    RewriteCond %{HTTP_HOST} ^yourdomain.com$
    RewriteRule ^/?(.*)$ "http\:\/\/www\.yourdomain\.com\/$1" [R=301,L]
    ```
    
    Replace yourdomain.com with your website address
3. This will ensure that when yourdomain.com is entered in the address bar it will redirect to www.yourdomain.com, this will help so that search engines won't pick up duplicate content for your website
