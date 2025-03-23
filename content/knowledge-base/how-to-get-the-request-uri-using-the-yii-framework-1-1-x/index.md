---
author: "icarnaghan"
title: "How to get the request URI using the Yii Framework 1.1.x"
date: 2018-03-22
---

The **Request URI** server variable forms part of the **Server** and **execution environment information** set

To get the **URI** within the **Yii Framework** use the following code

```
echo Yii::app()->request->getRequestUri(); //The same as echo $_SERVER['REQUEST_URI'];
```

This can be called from anywhere within your **Yii Framework** application
