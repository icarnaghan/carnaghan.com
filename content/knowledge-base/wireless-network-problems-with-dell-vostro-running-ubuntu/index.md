---
author: "icarnaghan"
title: "Wireless network problems with DELL Vostro running Ubuntu"
date: 2018-04-07
---

**Problem:** Can't connect to wireless network using Ubuntu together with Dell Vostro notebook or wireless light is not burning or any other wireless connectivity problems with the Dell Vostro running Ubuntu.

**Solution:**

The network service needs to be restarted once all the other services are started.

Add the line to the file **/etc/rc.local**

**/etc/init.d/networking restart** 

And reboot the PC and now it should work.
