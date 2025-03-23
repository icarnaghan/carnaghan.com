---
author: "icarnaghan"
title: "How to delete a Cookie in Yii Framework 1.1"
date: 2018-03-22
---

To delete all Cookies execute the following command:

```
Yii::app()->request->cookies->clear();
```

To delete a specific cookie execute the command below, only replacing **cookie\_name** with the name of your cookie:

```
unset(Yii::app()->request->cookies['cookie_name']);
```
