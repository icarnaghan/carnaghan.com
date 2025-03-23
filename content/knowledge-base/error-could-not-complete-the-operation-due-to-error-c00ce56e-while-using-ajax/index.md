---
author: "icarnaghan"
title: "Error: \"Could not complete the operation due to error c00ce56e\" while using Ajax"
date: 2018-03-21
---

I recently had a problem trying to load a PHP page into a DIV tag using Ajax. Everything worked fine in Firefox, Opera, Safari and Google Chrome, but there was no way for it to work in Internet Explorer 7. Personally I don't like Internet Explorer due to amount of problems I get while developing.

I tried to load the page into a DIV using JQuery. JQuery failed even thougt it's supposed to be cross-browser compatible.  Then I wrote my own Ajax code and that also didn't seem to work. As soon as the responseText needs to be called I get the following error in Internet Explorer 7 **"Could not complete the operation due to error c00ce56e".**

It looked like an encoding problem for me.

I solved the problem by adding the following lines at the top of my PHP file

**mb\_internal\_encoding("UTF-8"); header("Content-Type: text/html; charset="utf-8");**

**//This piece of code I added where I create my Database connection mysql\_query("SET NAMES 'utf8'");**

After adding these lines it worked in perfectly Internet Explorer 7.
