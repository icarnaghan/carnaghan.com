---
author: "icarnaghan"
title: "How to disable JQuery in the Yii Framework 1.1.x"
date: 2018-03-22
---

Include the following code anywhere in your application 

```
 
	
[js]<span id="urn:enhancement-f9965c67-8856-e15b-a96a-9ae613690f5b" class="textannotation">Yii</span>::<span id="urn:enhancement-0ff1ff82-84ee-005a-2d01-4a27dedfa994" class="textannotation">app</span>()->clientScript->scriptMap=array(
 
	        'jquery.js'=>false,

	);[/js]

```
