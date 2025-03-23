---
author: "icarnaghan"
title: "How to remove the top bar in Wordpress for logged-in users"
date: 2018-04-06
---

Edit the **functions.php** file in within your theme and add the following line to it

```
add_filter( 'show_admin_bar', '__return_false' );
```

This will remove the top bar when a user is logged-in.
