---
author: "icarnaghan"
title: "How to count the number of options in a select box using JQuery"
date: 2018-03-21
---

This can be done using the **jQuery** **length** property

You will use the following command to determine if there are any options within the select box.

```
var length = $('#selectBoxId > option').length;
console.log(length);
```

**#selectBoxId** should be replaced with the ID of your select box.
