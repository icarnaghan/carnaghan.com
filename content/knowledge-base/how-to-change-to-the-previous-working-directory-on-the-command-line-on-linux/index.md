---
author: "icarnaghan"
title: "How to change to the previous working directory on the command line on Linux"
date: 2018-04-07
---

Type in the command below to go to your **previous working directory**

```
cd -
```

or

```
cd $OLDPWD
```

**Points to remember**

- The **"-"** is short for **previous working directory**.
- The **previous working directory** is defined by the shell variable **$OLDPWD**.
- Everytime you use the **cd** command it sets the **$OLDPWD** environment variable.
- Thus **cd $OLDPWD** is the same as **cd -**
