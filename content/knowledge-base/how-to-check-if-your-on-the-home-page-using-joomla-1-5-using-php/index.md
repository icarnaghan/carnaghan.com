---
author: "icarnaghan"
title: "How to check if your on the Home page using Joomla! 1.5 using PHP"
date: 2018-03-30
---

Anywhere in your code place the following code

```
 
	if(JRequest::getVar('view') == "frontpage" ) :
 
	 echo "I'm on the Front Page";
 
	else :
 
	 echo "Not on the Front Page";
 
	endif;

```

The above code may be modified according to your needs
