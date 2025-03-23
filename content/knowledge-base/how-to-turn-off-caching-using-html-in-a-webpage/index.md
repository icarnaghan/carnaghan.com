---
author: "icarnaghan"
title: "How to turn off Caching using HTML in a webpage"
date: 2018-03-22
---

Add the following code between the <head> tags in your HTML page

```
<meta http-equiv="Expires" content="0" />
<meta http-equiv="Pragma" content="no-cache" />
<meta http-equiv="Cache-Control" content="no-cache, no-store, must-revalidate" />
```

The above should turn off webpage caching
