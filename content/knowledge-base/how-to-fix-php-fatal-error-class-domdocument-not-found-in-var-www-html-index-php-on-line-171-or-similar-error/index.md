---
author: "icarnaghan"
title: "How to fix PHP Fatal error: Class 'DOMDocument' not found in /var/www/html/index.php on line 171 or similar error"
date: 2018-04-07
---

**NOTE**: Received this error on a **Centos 5** environment while trying to run a **PHP** script that makes use of the **DOMDocument** class

 

In the **CLI** _(Command Line Interface)_ run the following command

{codecitation class="brush: shell;"} yum install php-xml {/codecitation}

This will install XML support and will solve the **DOMDocument** issue
