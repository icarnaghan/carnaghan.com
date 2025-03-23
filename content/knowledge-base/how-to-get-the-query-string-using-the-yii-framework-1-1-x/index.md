---
author: "icarnaghan"
title: "How to get the QUERY STRING using the Yii Framework 1.1.x"
date: 2018-03-22
---

The **QUERY STRING** server variable forms part of the **Server** and **execution environment information** set

To get the **QUERY STRING** within the **Yii Framework** use the following code

```
echo Yii::app()->request->getQueryString(); //The same as echo $_SERVER['QUERY_STRING'];
```

This can be called from anywhere within your **Yii Framework** application
