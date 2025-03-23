---
author: "icarnaghan"
title: "Tasktar in Ubuntu disappeared (Gnome Panel)"
date: 2018-04-07
---

What to do if your taskbar (GNOME Panel) disappeared in Ubuntu and you need to get it back, in our case we installed updates after unchecking some updates and after reboot the Gnome Panel was gone. So basically we assume that the panel does not exists anymore isn't installed anymore.

**Solution:**

In the Graphical Mode press ALT+CTRL+F2 together to get to the command line.

Enter your username and password and then type in the following command

**apt-get install gnome-panel** 

and now the system will install the panel again and the toolbar will be back again.
