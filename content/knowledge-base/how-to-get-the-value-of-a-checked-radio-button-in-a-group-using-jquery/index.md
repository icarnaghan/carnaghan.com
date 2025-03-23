---
author: "icarnaghan"
title: "How to get the value of a checked radio button in a group using JQuery"
date: 2018-03-21
---

Within your JQuery code use the following line of code to get the value

```
var radio_value = $("input[name='radio_group_name']:checked").val();
```
