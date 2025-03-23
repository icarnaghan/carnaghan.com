---
author: "icarnaghan"
title: "How to mount a Samba Share on Linux"
date: 2018-04-07
---

```
mount -t cifs -o username=YOURUSERNAME,password=YOUPASSWORD //server_name_or_ip/folder_to_mount /mnt/folder_to_mount_to/
```

By using the above command and by replacing the relevant fields with your details, you should be able to **mount** your **Samba Share** on **Linux**

_**Explanation:**_

- _**mount** = mounts a filesystem_
- _**\-t** = Used to indicate the filesystem type, in this case cifs_
- _**cifs** = Common Internet Filesystem_
- _**YOURUSERNAME** = Replace with your Samba Share Username_
- _**YOURPASSWORD** = Replace with your Samba Share Password_
- _**server\_name\_or\_ip** = Replace with your Server name or IP address_
- _**folder\_to\_mount** = Network share name/ folder_
- _**/mnt/folder\_to\_mount\_to** = The folder on the Linux machine you wish to mount the Drive to. Ensure that this folder exists_
