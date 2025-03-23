---
author: "icarnaghan"
title: "How to decode a JSON string using JavaScript"
date: 2018-03-21
---

If you have a **JSON** **encoded** **string** that you might have received from a **ajax** **script**and you need to **decode** it using **JavaScript** you can use the **_eval_()** function to **decode** the string. The _**eval()**_ function **evaluates** or **executes** an given argument.

**Example**:

```
var string = '{"id" : 32}'; 
var d = eval('(' + string + ')'); 
alert(d.id); //will alert 32
```
