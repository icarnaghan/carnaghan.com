---
author: "icarnaghan"
title: "How to use Font Awesome Icons as Bullets"
date: 2018-03-22
---

This could be accomplished by using the built in Font Awesome CSS classes

1. Add the **fa-ul** class to the **ul** html tag
2. Between the **li** tags add **<i class="fa-li fa fa-stop"></i>** replacing the **fa-stop**CSS class with the icon class you would like to show as the bullet

**Example:**

```
<ul class="fa-ul">
 <li><i class="fa-li fa fa-stop"></i>Bullet 1</il>
 <li><i class="fa-li fa fa-stop"></i>Bullet 2</il>
 <li><i class="fa-li fa fa-stop"></i>Bullet 3</il>
 <li><i class="fa-li fa fa-stop"></i>Bullet 4</il>
 <li><i class="fa-li fa fa-stop"></i>Bullet 5</il>
</ul>
```
