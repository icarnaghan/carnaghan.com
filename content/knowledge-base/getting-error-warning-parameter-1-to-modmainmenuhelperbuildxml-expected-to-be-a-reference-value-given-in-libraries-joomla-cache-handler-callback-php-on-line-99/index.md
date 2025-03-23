---
author: "icarnaghan"
title: "Getting error Warning: Parameter 1 to modMainMenuHelper::buildXML() expected to be a reference, value given in /libraries/joomla/cache/handler/callback.php on line 99"
date: 2018-03-30
---

This error happens because the version of **Joomla!** you are running is not compatible with **PHP 5.3.0** . You could get this error for the reason being that your host upgraded to **PHP 5.3.0**

A quick solution will be is to open the file **modules/mod\_mainmenu/helper.php** in your root folder and change the following line from

```
function buildXML(&$params)
```

to

```
function buildXML($params)
```

at the top of **helper.php**

The best solution will be to upgrade your **Joomla!** installation to the latest **Joomla!** release
