---
author: "icarnaghan"
title: "How to add JavaScript to you view files using the Yii Framework"
date: 2018-03-22
---

Add the JavaScript code as below to your view

```
	$js = Yii::app()->getClientScript();
 
	$js->registerScript(
 
	'my-javascript-id',
 
	'var value = "Hello World";
 
	alert(value);',
 
	CClientScript::POS_END );
```

Yii's **CClientScript** is used to place JavaScript to your views.

The arguments of register script are as follows:

- The first argument uniquely identifies your script
- The second argument contains your actual **JavaScript**
- The third argument sets the position where the **JavaScript** should be placed. In the example above the CClientScript::POS\_END specifies that the script will be placed before the closing _**</body>**_ tag.

More details about registerScript can be found here
