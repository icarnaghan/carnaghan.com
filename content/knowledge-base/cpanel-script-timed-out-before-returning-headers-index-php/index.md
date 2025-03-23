---
author: "icarnaghan"
title: "CPanel: Script timed out before returning headers: index.php"
date: 2018-04-07
---

_**Script timed out before returning headers: index.php**_ is sometimes caused by a badly written script, or the script took to long to execute.

To solve this problem on a **CPanel** server you have to slightly increase the **TimeOut**directive using **Web Host Manager "WHM"**.

To do this visit _**WHM > Apache Configuration > Global Configuration**_

Search for **TimeOut** and slightly increase it's value in seconds. If the error still exist, slightly increase this value until the problem is resolved. Once fixed, try to re-look at your script.
