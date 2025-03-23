---
author: "icarnaghan"
title: "How to find the id of the first anchor html element within the first element of an unordered list using JQuery"
date: 2018-03-21
---

With getting the id I mean getting the attribute id's value for the first element within the first element of the unordered list tag.

 

**Answer**:

We can obtain this by using the **:first** Selector from JQuery. Read more about the selector here

**Example**:

_HTML_ 

```
<ul class="custom_class">
    <li><a href="test1.html" id="1" name="link1" /></li>
    <li><a href="test2.html" id="2" name="link2" /></li>
    <li><a href="test3.html" id="3" name="link3" /></li>
    <li><a href="test4.html" id="4" name="link4" /></li>
    <li><a href="test5.html" id="5" name="link5" /></li>
</ul>
```

_JQuery_

```
        var id = $('.custom_class li a:first').attr('id');

```
