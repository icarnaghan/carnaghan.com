---
author: "icarnaghan"
title: "mount: unknown filesystem type 'exfat' - Fedora 20"
date: 2018-04-07
---

**Problem**: Getting error _**mount: unknown filesystem type 'exfat'**_ when  inserting USB flash drive to USB port using Fedora Core 20

**Solution**:

Execute the following commands:

1. ```
    wget ftp://rpmfind.net/linux/rpmfusion/free/fedora/releases/20/Everything/x86_64/os/fuse-exfat-1.0.1-1.fc20.x86_64.rpm
    ```
    
2. ```
    rpm -ivh fuse-exfat-1.0.1-1.fc20.x86_64.rpm
    ```
    
3. Re-Insert Device
