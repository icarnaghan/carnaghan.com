---
author: "icarnaghan"
title: "How to check if a checkbox has been checked using JQuery"
date: 2018-03-21
---

The following code checks if a checkbox has been checked

```
var checkBox = $("input[name='myCheckBox']:checked").val(); 
 
if(checkBox == 'on'){
   alert('CHECKED!!');
}else{
   alert('NOT CHECKED');
}
```

**myCheckBox** is the name of the checkbox element

e.g.

```
<input type="checkbox" name="myCheckBox" />
```
