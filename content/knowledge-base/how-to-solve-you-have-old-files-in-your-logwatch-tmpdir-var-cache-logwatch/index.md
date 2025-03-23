---
author: "icarnaghan"
title: "How to solve You have old files in your logwatch tmpdir (/var/cache/logwatch)"
date: 2018-04-07
---

- Edit **_/etc/logwatch/conf/logwatch.conf_** and override the **TmpDir** value by changing the default temp directory to **/tmp** from **/var/cache/logwatch**
- **/tmp** automatically gets **trimmed** by most Linux distributions meaning that there won't be a built up of old log files.
- Now delete the old files in **/var/cache/logwatch** using the command below:
    
    ```
    rm -rf /var/cache/logwatch/*
    ```
