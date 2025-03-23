---
author: "icarnaghan"
title: "Removing Dotted Outline Around Active Link using CSS"
date: 2018-03-22
---

When a link on a webpage becomes **Active** sometimes a Dotted Outline appears which might look ugly in certain circumstances.The CSS **outline** property should be used to remove or style the Dotted Outline.

If you want to remove this Dotted Outline from every active link on the webpage simply add the following code:

```
a {
   outline: 0;
}
```
