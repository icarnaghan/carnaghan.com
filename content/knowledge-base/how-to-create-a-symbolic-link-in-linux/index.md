---
author: "icarnaghan"
title: "How to create a symbolic link in Linux"
date: 2018-04-07
---

**What is a symbolic link?**

A symbolic link is a special file that points to another file on the system. When you access one of these files, it has a pathname stored inside it. Use this pathname to advance to the file or directory on the system represented by the pathname stored in the symbolic link.

**How to create a symbolic link?**

Create a symbolic link with the **ln** command with the **\-s** option

**Syntax:**  _ln -s source destination_

**Explanation:** source is either the absolute or relative path to the original version of the file, and destination is the name you want the link to have.

**Example:** $ ln -s /home/httpd/html/site /home/peter/public\_html

**Explanation of Example:** Creates a link to my home directory to my web files. If there's an error an error message will come up while attempting to create a symbolic link, and if successful no output will be displayed.
