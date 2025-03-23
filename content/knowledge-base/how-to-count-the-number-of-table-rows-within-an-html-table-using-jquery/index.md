---
author: "icarnaghan"
title: "How to count the number of table rows within an html table using JQuery"
date: 2018-03-21
---

```
var countRows = $('#tableID tr').length; 
alert(countRows)
```

or

```
var countRows = $('#tableID tr').size;
alert(countRows)
```

The selector takes all rows and then counts them.
