---
author: "icarnaghan"
title: "How to find files in a directory that where modified in the last 14 days using Linux"
date: 2018-04-07
---

Type in the following command

```
find /var/www/ -mtime -14
```

this will find all files that where modified within the last 14 days within the _**/var/www/**_ directory. We use the _**\-mtime**_ test to get all the modified files.

 

To only find _**.txt**_ files that were modified within the last 14 days within the _**/var/www/**_directory we would use this command

```
find /var/www/ -mtime -14 | grep '\.txt'
```
