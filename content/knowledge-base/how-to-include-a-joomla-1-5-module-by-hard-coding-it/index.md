---
author: "icarnaghan"
title: "How to include a Joomla! 1.5 Module by hard coding it"
date: 2018-03-30
---

- Import/Include the module helper
    
    ```
    jimport('joomla.application.module.helper');
    ```
    
- Call the _**getModule**_ method and reference it to the **_$module_** variable
    
    ```
    $module = & JModuleHelper::getModule('mod_search');
    ```
    
- Display it in the browser
    
    ```
    echo JModuleHelper::renderModule($module);
    ```
    
- Your code will look like this
    
    ```
    jimport('joomla.application.module.helper');
    $module = & JModuleHelper::getModule('mod_search');
    echo JModuleHelper::renderModule($module);
    ```
