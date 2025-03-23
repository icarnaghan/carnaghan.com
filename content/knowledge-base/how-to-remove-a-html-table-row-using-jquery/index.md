---
author: "icarnaghan"
title: "How to remove a html table row using JQuery"
date: 2018-03-21
---

Ensure that the **html table row** has an **id**

e.g.

```
<tr id="TABLE_ROW_ID"><td>I want to be removed</td></tr>
```

Now the **JQuery** code that you will need to remove the table row

```
$('#TABLE_ROW_ID').remove();
```

If you do not have an id for the table row, try using one of the **JQuery** **selectors** available here.
