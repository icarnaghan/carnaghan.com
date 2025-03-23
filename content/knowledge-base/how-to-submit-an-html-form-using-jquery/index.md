---
author: "icarnaghan"
title: "How to submit an HTML Form using JQuery"
date: 2018-03-21
---

For example you have a form with **id "_myform_"**

```
<form id="myform" action="submit.php">
  <input type="text" value="This is a test form" />
  <input type="button" id="mybutton" value="Save" />
</form>
```

Now  when the button with **id "_mybutton_"** is clicked we want to submit the form using the **JQuery submit() function** which executes each time the specified event is triggered. The code looks like the below 

```
<script type="texxt/javascript">
$('#mybutton').click(function() {
  $('#myform').submit();
});
 
</script>
```

Now whenever the **Button** with  **id "_mybutton_"** is clicked the **form** will **submit** to the _submit.php_ page.
