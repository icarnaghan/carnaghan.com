---
author: "icarnaghan"
title: "Warning: Missing argument 1 for JDocumentHTML::getBuffer()"
date: 2018-04-06
---

When you have upgraded from **Joomla! 1.5.0,1.5.1,1.5.2 to 1.5.3** and on the front end receive the error **Warning: Missing argument 1 for JDocumentHTML::getBuffer()** and don't know what to do. Follow the steps below in order to fix it.

**STEP 1**

Download the latest complete **Joomla! 1.5.3** or later from the **Joomla! Website**, and locate the following file in the installation package **/libraries/joomla/document/html/html.php**

**STEP 2**

Copy the **html.php** and overwrite the existing file to your existing **Joomla! installation**to the following directory **/public\_html/libraries/joomla/document/html/** refresh yoursite and the error should be gone.
