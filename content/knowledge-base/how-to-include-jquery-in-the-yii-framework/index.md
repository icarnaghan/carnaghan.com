---
author: "icarnaghan"
title: "How to include JQuery in the Yii Framework"
date: 2018-03-22
---

You can add the below code anywhere in your **Yii Application** and **JQuery** will be included in the rightful place in your application

```
Yii::app()->clientScript->registerCoreScript('jquery');
```
