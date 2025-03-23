---
author: "icarnaghan"
title: "How to convert FAT32 to NTFS in Windows XP"
date: 2018-03-24
---

- Reboot the PC into **Safe Mode with Command Prompt**. _This can be done by pressing **F8** during the boot process and a menu will appear, select **Safe Mode with Command Prompt**_
- In the **Command Prompt** type in the following command and hit the Enter key
    
    ```
    convert c: /fs:ntfs
    ```
    
- Now you should have a **NTFS** partition
