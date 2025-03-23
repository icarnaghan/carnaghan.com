---
author: "icarnaghan"
title: "How to use JQuery to make a field Read Only"
date: 2018-03-21
---

Say you have a **input text field** as below

```
 <input type="text" name="inputField" id="inputField" />
```

As soon as the page has finished loading we will make use of **JQuery** to make the input field **Read Only** so that the field can't be edited by the user.

We do it like this

```
<script type="text/javascript">
 
jQuery(document).ready(function($){
 
   $('#inputField').attr('readonly', 'readonly');
 
})
 
</script>
```
