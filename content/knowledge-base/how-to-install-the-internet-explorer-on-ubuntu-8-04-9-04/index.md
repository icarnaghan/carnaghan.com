---
author: "icarnaghan"
title: "How To Install The Internet Explorer On Ubuntu 8.04/9.04"
date: 2018-04-07
---

This tutorial will guide you how to install **Internet Explorer** on **UBUNTU** Linux via **IEs4Linux**. **IEs4Linux** only contains **Internet Explorer 5, 5.5 and 6**. **IEs4Linux** comes in handy especially for Web Developers who need to test their web applications on **Internet Explorer**.

**NOTE:** For security reasons only use **IEs4Linux** for **development** and not to surf the **Internet**.

**STEP 1**

Open the Terminal and execute the following: **sudo apt-get install wine cabextract binfmt-support**

This is needed to install some required packages

**STEP 2**

Now we need to download the **IEs4Linux** file using the following command via the terminal: **wget http://www.tatanka.com.br/ies4linux/downloads/ies4linux-latest.tar.gz**

**NOTE:** If the download file does not exists please try to find the location of the file via google

 

**STEP 3**

Locate the directory where the file has been downloaded via the terminal and run the following command to uncompress the gunzip file: **tar xvfz ies4linux-latest.tar.gz**

**STEP 4**

Now an new folder will appear in the current working directory with the name**ies4linux-\***

**STEP 5**

Re-locate to the **ies4linux** directory via the terminal by running the following command: **cd ies4linux-\* STEP 6**

And then type in the following command: **./ies4linux**

**STEP 7**

Next you'll see a window with different versions of Internet Explorer - select which versions you wish to install, mark the corresponding checkbox if you want support for **Flash (IE6 only)** and choose if you want to have launchers. Click on "**OK**" to proceed.

**NOTE:** To enable **IE7** go to the advanced options, **IE7** is still experimental and might not work properly.

**STEP 8**

The selected packages are now being installed

**STEP 9**

The last window will have a command of how to run **IE**, execute that command to run.
