---
author: "icarnaghan"
title: "How to install NTFS support in Centos 6.2"
date: 2018-04-07
---

1. Download the _**rpmforge**_ for **Centos 6**
    
    ```
    wget http://packages.sw.be/rpmforge-release/rpmforge-release-0.5.2-2.el6.rf.x86_64.rpm
    ```
    
2. Install the **_rpmforge_** for **Centos 6**
    
    ```
    rmp -Uvh rpmforge-release-0.5.2-2.el6.rf.x86_64.rpm
    ```
    
3. Now install the _**ntfs-3g**_ package
    
    ```
    yum install fuse-ntfs-3g
    ```
    
4. Now try mounting your **NTFS** drive and it should work
