---
author: "icarnaghan"
title: "How to display different menus for logged-in and logged-out users in Wordpress"
date: 2018-04-06
---

Add the following snippet of code in your theme to the location where you would like the menu's to be displayed.

```
<?php
if ( is_user_logged_in() ):
 wp_nav_menu( array( 'menu' => 'Loggedin' ) );
else:
 wp_nav_menu( array( 'theme_location' => 'primary' ) );
endif;
?>
```

Basically, what the code above does, it checks if the user is logged-in and then displays the LoggedIn menu, you may replace LoggedIn with your menu name.

If the user is not logged-in we display the primary menu.
