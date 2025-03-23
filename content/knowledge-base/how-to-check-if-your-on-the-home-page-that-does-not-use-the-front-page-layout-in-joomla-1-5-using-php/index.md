---
author: "icarnaghan"
title: "How to check if your on the Home Page that does not use the Front Page layout in Joomla! 1.5 using PHP"
date: 2018-03-30
---

Use the code below on any page in your Joomla! application, the code may be changed or modified according to your needs.

```
 
	$menu = &JSite::getMenu();
 
	if (JRequest::getInt('Itemid') == $menu->getDefault()):
 
	    echo "I'm on the Home Page";
 
	else:
 
	    echo "I'm not on the Home Page";
 
	endif;
```
