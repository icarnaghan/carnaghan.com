---
author: "icarnaghan"
title: "How to get the the value for a form element using JavaScript by ID"
date: 2018-03-21
---

If you have a text input box with **ID age** and you want to obtain the value for the text box via **JavaScript** use the **JavaScript** function **getElementById()** to get the value

Html input text box

```
<input type="text" name="age" id="age" value="12" />
```

JavaScript function

```
	<script type="text/javascript">
 
	var age = document.getElementById('age').value;
 
	</script>
```
