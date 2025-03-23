---
author: "icarnaghan"
title: "How to reset a forgotten Ubuntu password"
date: 2018-04-07
---

- Boot up your **System**
- When the **Grub** screen appears choose **"Ubuntu x.xx, kernal x.x.x-xx-generic (recovery mode)"**. _The x's are in the place of the version numbers_
- On the next screen select "**Drop to root shell prompt"**
- Once in the **root shell prompt** use the **passwd** command to reset your password
    
    ```
    password USERNAME
    ```
    
    Replace **USERNAME** with the username who's password you need to reset
- Next enter the following commands to force changed blocks to disk and reboot the System
    
    ```
    sync
    reboot -f
    ```
    
    **sync** = _Writes any data buffered in memory out to disk and ensures that everything in memory is written to disk._ **reboot -f** = _Reboots the system_. **\-f** _forces the system to reboot_
- After the **reboot**, you should be able to login with the new password.
