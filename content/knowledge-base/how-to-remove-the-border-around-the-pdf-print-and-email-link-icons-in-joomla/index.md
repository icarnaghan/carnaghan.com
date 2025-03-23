---
author: "icarnaghan"
title: "How to remove the border around the PDF, PRINT and Email link icons in Joomla!"
date: 2018-04-06
---

If you have a **Joomla! Template** and there is a border around the Small **PDF, Print and Email icons** and you wish to have the **border** removed and don't know how, then this tutorial could help you.

**STEP 1**

Locate the **Default templates \*.css** file, sometimes it's called **template.css**. The easiest way to find this is to access the **Template Manager** in Joomla!. In Joomla! 1.5 it's under **Extentions->Template Manager**. Select the current template and click on the **Edit** Button. And then select **Edit CSS**. Select the **templates \*.CSS file** and click on edit. Joomla! 1.0.x should be similar just the **Template Manager** would be under **Site->Template Manager->Site Template**

**STEP 2**

At the top or bottom of the file add the following lines

**img { border:0 none; }**

This should remove the **border**.

**STEP 3**

Refresh your page and the border should be gone.
