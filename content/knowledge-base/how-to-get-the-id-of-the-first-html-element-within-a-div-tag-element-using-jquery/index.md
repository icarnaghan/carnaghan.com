---
author: "icarnaghan"
title: "How to get the id of the first html element within a div tag element using JQuery"
date: 2018-03-21
---

How to get the id of the first img html tag element within a specific div tag using **JQuery**? With getting the id I mean getting the attribute id's value for the first element within the div tag.

 

**Answer**:

We can obtain this by using the **:first** Selector from JQuery. Read more about the selector here

**Example**:

_HTML_

<div class="custom\_div">

```
    <img id="1" name="image1" src="myImage1.jpg" width="200" border="1" />
    <img id="2" name="image2" src="myImage2.jpg" width="200" border="1" />
    <img id="5" name="image3" src="myImage3.jpg" width="200" border="1" />
 
</div>
```

_JQuery_

```
        var id = $('.custom_div img:first').attr('id');

```
