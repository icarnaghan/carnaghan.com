---
author: "icarnaghan"
title: "Getting PHP Fatal error: Can't use function return value in write context"
date: 2018-03-22
---

Make sure that you did not include a **function** within the _**empty**_ PHP function. eg

```
if(empty(getUsers())){}
```
