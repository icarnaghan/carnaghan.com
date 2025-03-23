---
author: "icarnaghan"
title: "How do I hide and show HTML elements using JQuery without any special effects?"
date: 2018-03-21
---

This can be done by using the **hide()** and **show()** methods or the **toggle()** method. The **toggle()** method calls the **show()** method if the element is **hidden** and the **hide()**method if the element is **showing**.

**$("selector").hide(); $("selector").show();**

or

**$("selector").toggle();**

**Example**:

_<script type="text/javascript">_

$(function() { $("#mybutton").click(function() { **$("#div\_id").toggle();** }); });

_</script>_

<div id="**div\_id**"> This is an Example. </div>

<input type="button" id="mybutton" value="**Hide/Show Div**">

Basically everytime the **button** is **clicked** it **hides** the **div tag**. If the **div tag** is **showing** it hides it and **shows** the **div tag** if the **div tag** is **hidden**. The **toggle()**method could also be replaced with **$("#div\_id").hide();** and **$("#div\_id").show();** but then the **function** needs to be changed a bit in order to have it working as above.
