---
author: "icarnaghan"
title: "How to check if the CURL extention is installed and compiled with PHP"
date: 2018-03-22
---

Add this line of code to a PHP script

```
var_dump(curl_version());
```

If there was a error similar to this **Fatal error: Call to undefined function curl\_version()** or no results was shown, it means that **CURL** is not installed.
