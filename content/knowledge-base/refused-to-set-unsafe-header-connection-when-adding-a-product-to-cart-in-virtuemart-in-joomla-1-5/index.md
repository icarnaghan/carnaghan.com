---
author: "icarnaghan"
title: "Refused to set unsafe header \"Connection\" when adding a product to cart in Virtuemart in Joomla! 1.5"
date: 2018-03-25
---

**Complete Error:**

_Refused to set unsafe header "Connection" XMLHttpRequest cannot load http://www.yourdomain.com/index.php. Origin http://yourdomain.com is not allowed by Access-Control-Allow-Origin._

This seems to happen whenever you access your domain via the domain url without the www record. So the Ajax calls that are made when adding a product to the cart seem to make calls to the _**www.yourdomain.com**_ url and sees it as a different website.

A simple workaround is to place the following in your _**.htaccess**_ file

```
RewriteEngine on
 
RewriteCond %{http_host} ^yourdomain.com$ [nc]
 
RewriteRule ^(.*)$ http://www.yourdomain.com/$1 [r=301,nc]
```

Also remember to replace yourdomain.com with your website domain name
