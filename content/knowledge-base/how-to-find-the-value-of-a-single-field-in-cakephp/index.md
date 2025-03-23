---
author: "icarnaghan"
title: "How to find the value of a single field in cakePHP"
date: 2018-03-22
---

Use the model method _**field**_ if no matching data is found it returns false.

**Example**

```
 
	$this->Model->id = 10;
 
	$this->Model->field('name');
```

The example above displays the value of the **name** **field** in the **database** where the **id**is **equal** to 10

Read more here
