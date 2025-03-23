---
author: "icarnaghan"
title: "How to permanently display a module inside a Component in Joomla!"
date: 2018-03-30
---

In the template or any other place in the Joomla! Components code where you wish to display the module permanently place the following PHP code

```
jimport('joomla.application.module.helper'); //Importing the Module helper
$module = & JModuleHelper::getModule('mod_name');
echo JModuleHelper::renderModule($module); //rendering the module
```

Replace **_mod\_name_** with your module's name
