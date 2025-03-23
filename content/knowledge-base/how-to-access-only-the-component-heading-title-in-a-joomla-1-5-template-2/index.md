---
author: "icarnaghan"
title: "How to access only the Component heading/title in a Joomla! 1.5 template"
date: 2018-04-06
---

How to access only the **component heading/title** in a **Joomla! 1.5****template** when building a new **template** and the **component heading** needs to be in a **strategic** place on the **template.**

**Answer**:

Insert the following code where you need to have the **component heading** displayed on the template.

_//Open PHP tag_ **<?php** _//First we instantiate the document object, to get all document details._  $document =& JFactory::getDocument();

_//Now we echo the component heading by echoing the **getTitle()** method of the **getDocument** class_  echo $document->getTitle();

_//Closing PHP tag_ **?>**   

**NOTE**: This has been tested in **Joomla! 1.5.10**. I don't think this is the right method to do this, only use this if absolutely neccesary.
