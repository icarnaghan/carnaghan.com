---
author: "icarnaghan"
title: "How to get information about a file such as last access, modified or changed time using Linux"
date: 2018-04-07
---

**NOTE**: Tested and tried on Ubuntu 9.04

 

**Answer**:

By using the '**stat**' command.

**stat** = _Display file or file system status_

**Example**:

Input:

```
stat photos-20090916-0.db
```

Output:

```
File: `photos-20090916-0.db'
Size: 3072          Blocks: 8          IO Block: 4096   regular file
Device: 807h/2055d    Inode: 529743      Links: 1
Access: (0644/-rw-r--r--)  Uid: ( 1000/  user)   Gid: ( 1000/  user)
Access: 2009-09-16 08:22:12.085106864 +0200
Modify: 2009-09-16 08:22:11.490127752 +0200
Change: 2009-09-16 08:22:11.526128486 +0200

```
