---
author: "icarnaghan"
title: "How to add a new options to JQuery Chosen Plugin Dynamically"
date: 2018-03-21
---

If **users** is the **id** of the select **Chosen** dropdown box, then use **JQuery** to append new options dynamically as in the example below

```
$("#users").append('<option value="1">User</option>').trigger("chosen:updated");
```

**.trigger("chosen:updated");**  refreshes the Chosen dropdown box with the new option.
