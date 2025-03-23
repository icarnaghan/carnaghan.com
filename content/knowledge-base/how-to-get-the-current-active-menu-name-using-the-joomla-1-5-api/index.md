---
author: "icarnaghan"
title: "How to get the current active menu name using the Joomla! 1.5 api"
date: 2018-03-30
---

By typing the code below within the appropriate place the active menu item name will be echoed to the browser

```
<?php echo JSite::getMenu()->getActive()->name; ?>
```

To read more about the **JSite class** click here
