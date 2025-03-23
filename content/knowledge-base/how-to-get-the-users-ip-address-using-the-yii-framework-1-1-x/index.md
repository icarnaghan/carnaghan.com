---
author: "icarnaghan"
title: "How to get the user's IP Address using the Yii Framework 1.1.x"
date: 2018-03-22
---

The **Host Address** server variable forms part of the **Server** and **execution environment information** set

To get the user's **IP ADDRESS** within the **Yii Framework** use the following code

```
echo Yii::app()->request->userHostAddress;
```

This can be called from anywhere within your **Yii Framework** application
