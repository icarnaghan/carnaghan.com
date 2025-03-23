---
author: "icarnaghan"
title: "How to migrate from Thunderbird to Evolution Mail together with all folders and sub folders all at once"
date: 2018-04-06
---

**NOTE**: This tutorial is aimed at **Ubuntu** users.

1. Open the **home** directory
2. Select you're username
3. Press **CTRL+H** together to reveal hidden files and folders and locate **.mozilla-thunderbird** and **.evolution**
4. Copy everything from **~/.mozilla-thunderbird/zyx.default/Mail** into**~/.evolution/mail/local/Inbox.sbd/**  **NOTE**: Copy only the **.mbox** files and delete**.****msf** files.
5. Restart **Evolution Mail** and all you're mails should be there.

**NOTE**: This is a short and easy solution if you have lots of folders in **Thunderbird**.
