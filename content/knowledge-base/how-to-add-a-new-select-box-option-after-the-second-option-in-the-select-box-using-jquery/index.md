---
author: "icarnaghan"
title: "How to add a new Select Box option after the second option in the Select Box using JQuery"
date: 2018-03-21
---

```
<select id="options">
 <option>Option 1</option>
 <option>Option 2</option>
 <option>Option 3</option>
</select>
```

If you want to add a new option under Option 1, you would need to use the JQuery after function as example below

```
$("#options option:first").after("<option>New second option</option>");
```

The above will find the first option and then add the second option under the first option withing the select element with id options
