---
author: "icarnaghan"
title: "How to copy files over SSH using SCP Linux command line tool"
date: 2018-04-07
---

**SCP** = **SECURE COPY** (remote file copy program), with **SCP** you can **copy** files over an **SSH connection securely** and **encrypted**. With this **Linux command line tool**you can **copy** files **remotely** from one **remote server** to another, or from you're PC to a **remote server**.

**USAGE** = scp \[-1246BCpqrv\] \[-c cipher\] \[-F ssh\_config\] \[-i identity\_file\] \[-l limit\] \[-o ssh\_option\] \[-P port\] \[-S program\] \[\[user@\]host1:\]file1 ... \[\[user@\]host2:\]file2

**OPTIONS** = Open a **terminal window** on you're **Linux** box, or/and type in the **command** **line** the following **command** for all **options** for **scp**: **man scp** **EXAMPLE** = **scp DevServer****.test.lan:/var/www/html/testSite/images/image1.jpg****testserver:/var/www/html/images/NewImages**
