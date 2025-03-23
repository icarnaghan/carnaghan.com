---
author: "icarnaghan"
title: "How to check if a Request was made via AJAX in PHP"
date: 2018-03-22
---

```
// Check for Ajax Request  
if (isset($_SERVER['HTTP_X_REQUESTED_WITH']) && strtolower($_SERVER['HTTP_X_REQUESTED_WITH']) === 'xmlhttprequest') {
    //Do stuff here
}
```
