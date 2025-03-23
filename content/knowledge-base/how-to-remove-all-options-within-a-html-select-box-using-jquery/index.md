---
author: "icarnaghan"
title: "How to remove all options within a Html select box using JQuery"
date: 2018-03-21
---

You have a **html select box** "_combo box_"  

```
<select id="selectBox">
<option>1</option>
<option>2</option>
<option>3</option>
<option>4</option>
</select>
```

In order to remove all items using **JQuery** use the **JQuery** _**empty**_ function

```
$('#selectBox').empty();
```

Replace **_selectBox_** with the relevant **_id_** for the select box

If you wish to **empty** the **select box** and add a single **option** to the **select box**, use **JQuery's** _**append**_ function together with the _**empty**_ function

```
$('#selectBox').empty().append('<option>New Option</option>');
```

This will add the New Option to the **select box**.
