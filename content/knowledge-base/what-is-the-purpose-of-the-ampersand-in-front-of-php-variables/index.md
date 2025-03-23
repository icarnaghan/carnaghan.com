---
author: "icarnaghan"
title: "What is the purpose of the & Ampersand in front of PHP Variables"
date: 2018-03-22
---

What this does it creates a **reference** to the **original variable** and thus does not **copy** the value of the **original variable**.

**$original\_var = 500**;

**&$ref\_var = $original\_var;**

_//This will print the value 500_ **echo  $ref\_var;**

_//Now we change the value of the original variable to 600_ **$original\_var = 600;**

_//Now we print the value of the reference variable, and the reference variable takes the value of the original variable_ **echo  $ref\_var;**  _//This will print 600_

- You can also **reference** **objects**
- Referencing variables come in handy when trying to accomplish two task at once

**NOTE**: **PHP 5** currently supports this
