---
author: "icarnaghan"
title: "How to remove a Linux partition from Windows XP and restoring the Master Boot Record"
date: 2018-03-24
---

1. Open **Control Panel**
2. Search for and open **Administrative Tools**
3. Locate **Computer Management** and then **Disk Management**
4. There will be a partition named **Unknown Partition** where the Linux Operating System has been installed
5. **Right Click** on the partition and **Delete Logical Drive**
6. After the **Logical Drive** has been deleted, format the deleted partition with the **FAT32 filesystem** so that **Windows** will recognize it.

After the above steps have been done, you will need to **Restore** the **Master Boot Record.** To restore the **Master Boot Record** you will need to execute the following **DOS** commands, you can either use your **Windows XP** boot disk to do this or the **Command Prompt**

1. In DOS type **c:\\**
2. Type **fdisk /mbr
    
    **

If the above does not work you can use your **Windows XP** disc to run the **Recovery Console**
