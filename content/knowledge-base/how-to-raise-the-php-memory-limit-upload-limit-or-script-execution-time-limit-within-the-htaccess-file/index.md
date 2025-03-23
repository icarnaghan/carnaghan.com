---
author: "icarnaghan"
title: "How to raise the PHP memory limit, upload limit, or script execution time limit within the .htaccess file"
date: 2018-03-22
---

Open your **.htaccess** file and add the line below to it

```
php_value memory_limit 40M
```

This will **increase** the **PHP memory limit**, if the altering of the **.htaccess** file is allowed
