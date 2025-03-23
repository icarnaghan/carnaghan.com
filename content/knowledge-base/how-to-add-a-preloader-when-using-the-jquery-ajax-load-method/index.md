---
author: "icarnaghan"
title: "How to add a preloader when using the JQuery ajax load method"
date: 2018-03-21
---

Usually there will be a **div** tag with an **ID** in which you will load the content.

**Example:** <div id="load"></div>

Now in order to have a **preloader** displayed while the **content** is busy loading we need to include the following code within the **function** used to load the content.

**function** load(){ //This is the function that loads the preloader $('#load').html('<img src="/images/ajax-loader.gif " />');

//This is the load function that loads the actual content and replaces the loader with the content $('#load').load('content.php'); }

The **preloader** will load first into the **div** tag once the function has been called. In the meantime the content will load and once the content has been loaded it will replace the **preloader** with the content.

**NOTE**: To find cool Ajax preloaders visit Ajaxload by clicking here.
