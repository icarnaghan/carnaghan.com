---
author: "icarnaghan"
title: "How to download a file using the Command Line"
date: 2018-04-07
---

If you need to download a file via the command line of Linux (eg. If you are logged in via SSH and need to download something). Please follow the steps below in order to download using the command line.

**STEP 1**

We use the **wget** command in order to download a file.

Most Linux distributions already have the wget command installed, if not we need to install it.

To check if **wget** is installed enter the following command. **which wget** after entering it press enter and then you should see something like this if it's installed **/usr/bin/wget**

**STEP 2**

If wget is installed skip this step and proceed to Step 3

How to install wget (Different distributions use different methods to install)

**DEBIAN/UBUNTU**

COMMAND: apt-get install wget

**FEDORA / CENTOS**

COMMAND: yum install wget

**STEP 3**

Now we proceed to the actual download

**Downloading a single page**

COMMAND:  wget http://www.sitename.co.za/test.pdf

**Downloading a entire site we use the recursive option**

COMMAND: wget -r http://www.sitename.co.za

**Downloading only certain file types from the site you wish to download using the -A option**

COMMAND: wget -r -A pdf,jpg http://www.sitename.co.za

**Downloading only external links, usually wget does not do this, here we can use -H option.**

COMMAND: wget -r -H -A pdf,jpg http://www.sitename.co.za

**By default wget will follow 5 levels when using -r option, we can change this behaviour with the -l option.**

COMMAND: wget -r -l 4
