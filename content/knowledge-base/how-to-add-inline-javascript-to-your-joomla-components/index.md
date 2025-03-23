---
author: "icarnaghan"
title: "How to add inline JavaScript to your Joomla! components"
date: 2018-03-25
---

JavaScript code can directly be declared within a component or module's display view

```
<?php
$document = &JFactory::getDocument();
$document->addScriptDeclaration('
 
 alert("An inline JavaScript Declaration");
 
');
?>
```

For more information visit: http://docs.joomla.org/Adding\_JavaScript

```
<?php
$document = &JFactory::getDocument();
$document->addScriptDeclaration('
    window.event("domready", function() {
        alert("An inline JavaScript Declaration");
    });
');
?>
```
