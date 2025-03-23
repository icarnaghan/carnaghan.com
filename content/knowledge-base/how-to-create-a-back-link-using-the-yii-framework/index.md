---
author: "icarnaghan"
title: "How to create a back link using the Yii Framework"
date: 2018-03-22
---

In the **view** that you wish to use add the following code for the back link.

```
CHtml::link('Back',Yii::app()->request->urlReferrer);
```
