---
author: "icarnaghan"
title: "PHP Fatal error: Call to undefined function mb_detect_encoding()"
date: 2018-04-07
---

How to fix this error

```
PHP Fatal error:  Call to undefined function mb_detect_encoding()
```

when trying to use the _**mb\_detect\_encoding** PHP function_

 

This means that the _**php-mbstring**_ extention needs to be installed

 

To install this on a Centos server run the following command from the command line

```
yum install php-mbstring
```

and then restart the Apache web server by using this command as root

```
service httpd restart
```
