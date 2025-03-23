---
author: "icarnaghan"
title: "Infinite loop detected in JError, how to solve"
date: 2018-03-25
---

Recently I moved my Joomla! 1.7 website from one server to another, then I received this error **Infinite loop detected in JError**

The solution to this was that my Database details were incorrect in the **configuration.php** file, after correcting it the site was up and running again
