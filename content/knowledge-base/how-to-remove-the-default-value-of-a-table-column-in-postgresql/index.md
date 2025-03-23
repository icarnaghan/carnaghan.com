---
author: "icarnaghan"
title: "How to remove the DEFAULT value of a table column in PostgreSQL"
date: 2018-04-07
---

Execute the following command

```
ALTER TABLE your_table ALTER COLUMN your_column DROP DEFAULT;
```

Replace **your\_table** with the **table** and **your\_column** with the **column nam**e where you wish to remove the default value

The above command is the same as setting the **DEFAULT** to **NULL**
