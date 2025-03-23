---
author: "icarnaghan"
title: "How to get current controller name and action name in Yii"
date: 2018-03-22
---

```
$controller=Yii::app()->controller;
 
$action=$controller->action;
 
 
//Getting the current action
 
echo $action->id;
 
 
 
//Getting the current controller
 
$controller->uniqueID
```
