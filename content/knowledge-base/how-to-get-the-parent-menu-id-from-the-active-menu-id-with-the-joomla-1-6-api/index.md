---
author: "icarnaghan"
title: "How to get the parent menu id from the active menu id with the Joomla! 1.6 API"
date: 2018-03-25
---

1. This can be done using the _**getActive()**_ method from the **JMenu** class with the **Application** **subpackage**. _Read More here_
2. Anywhere in your **Joomla! code** use the following **codeline** to get the **parent ID**for the **active id**.
    
    ```
    $parentID = JSite::getMenu()->getActive()->tree[0];
    ```
