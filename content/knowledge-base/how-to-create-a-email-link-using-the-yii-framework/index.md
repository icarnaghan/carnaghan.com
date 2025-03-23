---
author: "icarnaghan"
title: "How to create a Email link using the Yii Framework"
date: 2018-03-22
---

In the **view** that you wish to use add the following code for the Email link.

```
CHtml::mailto($data->email)
```

**NOTE**: $data->email contains the email address, replace this variable with the relevant email address or variable that contains the email address.
