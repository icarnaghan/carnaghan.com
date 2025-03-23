---
author: "icarnaghan"
title: "How to force your website to use https instead of http via the .htaccess file"
date: 2018-03-22
---

Did you recently install a **SSL Certificate** for your domain and need to force access to your website via **https** instead of **http**?

This can be done using the **mod\_rewrite** Module with the **Apache HTTP Server.**

Add the following code to your **.htaccess** file, save and refresh your website.

```
RewriteEngine On
RewriteCond %{HTTPS} !=on
RewriteRule ^ https://%{HTTP_HOST}%{REQUEST_URI} [L,R=301]
```

This permanently redirect all **http** request to **https**
