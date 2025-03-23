---
author: "icarnaghan"
title: "How to get the value of an HTML element by the attribute name instead of the attribute id using JQuery"
date: 2018-03-21
---

This can be accomplished by using the name attribute selector

```
$("input[name=ElementName]").val();
```

**ElementName** is the **attribute name** of the element

```
<input type="text" name="ElementName" />
```
