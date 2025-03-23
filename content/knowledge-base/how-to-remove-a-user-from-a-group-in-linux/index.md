---
author: "icarnaghan"
title: "How to remove a user from a group in Linux"
date: 2018-04-07
---

Use the **gpasswd** command. The **gpasswd** command is used to administer /etc/group, and /etc/gshadow.

Use to following command:

```
sudo gpasswd -d user group
```

Replace user with the user you wish to remove and group with the group. The _**\-d**_option is to remove the user from the named group.
