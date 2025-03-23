---
author: "icarnaghan"
title: "How to mount partition/drive at startup Ubuntu/Linux"
date: 2018-04-07
---

1. Open a new **Terminal Window**
2. Create a **mount point** where you need the **partition/drive** to be **mounted**. You may **mount** the **drive** anywhere and call it whatever you want to. **Example:** mkdir /media/development  
3. Make a backup of the **fstab** file!!!  This is very important!!!!!! **Example:** sudo cp /etc/fstab /etc/fstab.backup20090728
4. Open the **fstab** file for editing **Example:** sudo gedit /etc/fstab
5. Add the line below at the end of the fstab file /dev/sda8    /media/development    vfat    defaults    0    0
    1. _Replace ntfs with vfat if fat32 partition or ext3/ext4_
    2. /dev/sda8 = _drive/partition_
    3. /development = _mounting point_
    4. ntfs = _filesystem_
6. Type in 'sudo mount -a' to refresh the **fstab** or reboot PC for changes to take effect.
7. Locate the mounting point **Example:** cd /media/development
8. Drive should be mounted successfully but only root user will have permission to write to the mounted drive.
9. Modify the last added line in the **fstab** file to read as below so that the given user is able to write to the drive /dev/sda8    /media/development    vfat   uid=uname,gid=users,utf8=true    0    0
