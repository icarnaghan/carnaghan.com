---
author: "icarnaghan"
title: "How to package/ backup a CPanel account from the command line"
date: 2018-04-07
---

This can be done by running the /scripts/pkgacct script from the cli. Running this command will create a **cpmove** archive which can be used to restore on another cpanel server.

**Usage**:

```
/scripts/pkgacct [arguments] username destination
```

**Example**:

```
/scripts/pkgacct accountusername /tmp
```

The above command will create a full backup and store the archive in the tmp directory.
