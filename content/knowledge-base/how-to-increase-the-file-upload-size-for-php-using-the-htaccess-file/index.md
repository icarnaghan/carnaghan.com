---
author: "icarnaghan"
title: "How to increase the file upload size for PHP using the .htaccess file"
date: 2018-03-22
---

Copy the following lines into your _**.htaccess**_ file, you may adjust the values as you see fit 

```
	php_value upload_max_filesize 10M
 
	php_value post_max_size 20M
 
	php_value memory_limit 128M
```
