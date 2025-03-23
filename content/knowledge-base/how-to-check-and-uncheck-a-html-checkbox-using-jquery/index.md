---
author: "icarnaghan"
title: "How to check and uncheck a html checkbox using JQuery"
date: 2018-03-21
---

We will use a **checkbox** with **ID** _**"myCheckbox"**_ in this example

First to check a checkbox using **JQuery** use the following code, remember to replace _**"myCheckbox"**_ with the **ID** of your **checkbox**

```
$('#myCheckbox').attr('checked','checked');
```

To **un-check** the **checkbox** use the following **JQuery** code, remember to replace _**"myCheckbox"**_ with the **ID** of your **checkbox**

```
$('#myCheckbox').removeAttr('checked');
```
