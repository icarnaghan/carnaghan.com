---
author: "icarnaghan"
title: "Text is unreadable when clinking Print, Email button to preview print, email page in Joomla!"
date: 2018-04-06
---

If you have an image for the Background in your Joomla! template, you will notice that if you click on the Print preview buttons, or Email buttons that the text is unreadable due to that the background image that is quite dark and that the text disappears in the image. When the Font is also dark almost the same color as the Background it also does this. Please follow the steps below to implement the solution.

**STEP 1**

Add the following lines at the top of your template css file (Joomla! 1.5 **EXTENSIONS=>TEMPLATE MANAGER=>EDIT=>EDIT CSS**)

**body.contentpane { background: #FFFFFF; padding-left : 3px; }**

The padding is optional, I only added padding so that the text isn't right against the border. #FFFFFF = White Background Color
