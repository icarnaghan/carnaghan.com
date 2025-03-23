---
author: "icarnaghan"
title: "Firefox Flash Player Problems with Ubuntu 9.04"
date: 2018-04-07
---

When loading **Flash enabled websites** in **Firefox** I get **Flash Player** problems? I'm running **Firefox 3.0.13** on **Ubuntu 9.04**

**Examples**:

- When loading Google Analytics some **flash features** like the **Dashboard**, **Visitors Overview** and **Map Overlay** just load the whole time without any results displaying.
- Some sites eg. www.sterkinekor.co.za does not work properly in **Firefox**.
- **General Flash Problems** occur when loading **Flash Websites**.

 

Somehow this problem occurs even if the latest **Adobe Fash Player** has been installed, reason being is that **Firefox** still uses an old version of the **Flash Player Plugin**.

To view the version of the **Flash Player Plugin** that **Firefox** uses follow the steps below.

1. Open **Firefox**.
2. In the URL address bar type in "**about:plugins**"
3. Locate the **Shockwave** **Flash Plugin** and there you'll find the version you use.
    
    ![Flash Version](images/flash1.png "Flash Version")

In order to solve this problem follow the steps below.

**Solution**:

1. In **Ubuntu** open your home directory. eg. **/home/yourName/**
2. Press **Ctrl+H** together in order to view hidden files and folders.
3. Locate the **.mozilla** folder and create a backup of this folder.
4. Now delete the **.mozilla** folder from your home directory. _(Ensure that you made a backup of this folder)_
5. Open **Synaptic Package Manager
    
    **![Synaptic Package Manager](images/flash2.png "Synaptic Package Manager")
6. Now uninstall all **Flash** and **Firefox** packages using **Synaptic Package Manager**. This can be accomplished by searching for **Firefox** and **Flash** using **Synaptic**, untick the checkboxes next to these packages and click on **Apply** to uninstall.
7. Now after the uninstall, install **adobe-flashplugin** via **Synaptic Package Manager**.
    
    ![Adobe Flash Plugin](images/flash3.png "Adobe Flash Plugin")
8. Once **Adobe Flash Player** has been installed install **Firefox** via **Sypnaptic Package Manager**.
    
    ![Firefox](images/flash4.png "Firefox")
9. Now copy your backup **.mozilla** folder to your home directory and overwrite the existing .**mozilla** folder.
10. Restart **Firefox** and load a **Flash web site** and the problem should be solved.
