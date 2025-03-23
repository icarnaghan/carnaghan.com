---
author: "icarnaghan"
title: "How to detect the data type of a PHP variable"
date: 2018-03-22
---

The **data type** of a **PHP** **variable** can be **detected** by using the built-in **PHP** **function****gettype()** _(PHP 4, PHP 5)_

_Example:_

```
$var ="This is a sentence"

echo $var; //This will return "string"
```

The following **possible values** can be **returned**:

- boolean
- integer
- double
- string
- array
- object
- resource
- NULL
- unknown type
