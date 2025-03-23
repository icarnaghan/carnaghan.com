---
author: "icarnaghan"
title: "How to check in Controller which validation rule failed in cakePHP"
date: 2018-03-22
---

Put the code below in your controller and replace the model name with the appropriate model name against which to check.

```
$errors = $this->ModelName->invalidFields();
```

The above code will return a array containing the validation rules that failed.

To read more about **validating** data in **cakePHP** click here
