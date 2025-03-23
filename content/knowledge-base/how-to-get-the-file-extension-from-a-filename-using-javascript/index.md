---
author: "icarnaghan"
title: "How to get the file extension from a filename using Javascript"
date: 2018-03-21
---

```
var filename = 'myFile.jpg';
var ext = filename.split('.').pop();  //We split the filename on every instance where the . is found and then getting the last element in the array using the pop() function 
alert(ext);
```
