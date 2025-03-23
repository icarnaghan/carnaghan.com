---
author: "icarnaghan"
title: "How to register/include the JQuery UI in the Yii Framework 1.1.x"
date: 2018-03-22
---

Include the following code anywhere in your application

```
Yii::app()->clientScript->registerCoreScript('jquery.ui');
```

The code abouve will register **jquery-ui** in your application
