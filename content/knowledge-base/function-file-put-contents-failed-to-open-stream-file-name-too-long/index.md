---
author: "icarnaghan"
title: "[function.file-put-contents]: failed to open stream: File name too long"
date: 2018-03-22
---

**Error:** \[<a href='function.file-put-contents'>function.file-put-contents</a>\]: failed to open stream: File name too long

To solve this error you need to rename the filename so that the filename and extention together are no more than 255 characters, an easy way to do this is

```
$filename=substr($name,0,251).'.pdf';
```

Note, that we used the character count 251 since 251 + the 4 characters for the extention together add up to 255 characters.
