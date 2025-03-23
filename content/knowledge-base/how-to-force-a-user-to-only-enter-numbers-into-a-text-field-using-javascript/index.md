---
author: "icarnaghan"
title: "How to force a user to only enter numbers into a text field using JavaScript"
date: 2018-03-21
---

Add the following **JavaScript** **function** to your **HTML** page

```
 
	function isNumberKey(evt)
	{
	     var charCode = (evt.which) ? evt.which : event.keyCode
	     if (charCode > 31 && (charCode < 48 || charCode > 57))
	        return false;
 
	     return true;
	}
```

The above function checks the input of the user and then returns false if no number has been entered and true if a number has been entered

Then in your **textfield HTML code** add the following

```
onkeypress="return isNumberKey(event)"
```

This will check for a number on every key press from the user

```
<input type="text" onkeypress="return isNumberKey(event)"  name="number" />
```
