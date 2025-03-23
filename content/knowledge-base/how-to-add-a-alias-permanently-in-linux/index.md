---
author: "icarnaghan"
title: "How to add a alias permanently in Linux"
date: 2018-04-07
---

Edit **/etc/bashrc** using

```
vim /etc/bashrc
```

add your alias to the file, for example if **ll** should be the alias for **ls -l** then add

```
alias ll="ls -l"
```

to **/etc/bashrc** and save the file.

 

For changes to take immediate effect execute the following command:

```
. ~/.bashrc
```
