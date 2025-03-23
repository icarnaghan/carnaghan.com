---
author: "icarnaghan"
title: "How to delete Komodo Edit 6 in Ubuntu"
date: 2018-04-07
---

- Delete the **Komodo** directory that the **Komodo Edit** installer created. If you do not know where that directory is use the **locate** command on the command line to locate the **Komodo** folder. eg.
    
    ```
    locate komodo
    ```
    
- Once found delete the **Komodo Edit 6** folder
    
    ```
    sudo rm -rf /home/USERNAME/Komodo-Edit-6/{/bash} Replace USERNAME with your name or user name that you use to loginTo delete all your Komodo Edit preferences/settings delete the ~/.komodo directory eg. {code bash}sudo rm -rf /home/USERNAME/.komodoedit/
    ```
    
    Replace **USERNAME** with your **name** or **user name** that you use to login
- Also delete all other **komodo** **files** and **folders**, locate them by using the **locate**command as stated above
    
    ```
    sudo rm /usr/local/bin/komodo
    sudo rm /home/USERNAME/.local/share/applications/userapp-komodo-*
    
    ```
