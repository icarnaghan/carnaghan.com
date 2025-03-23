---
author: "icarnaghan"
title: "How to add a CSS styled tooltip to your Joomla! 1.5 website"
date: 2018-03-30
---

In your code add the following code to activate the **tooltip behavior**

```
JHTML::_('behavior.tooltip');
```

This only needs to be added once per file. A good place to put it is just underneath the **defined('\_JEXEC') or die('Restricted access');** at the top of the page.

The tooltip behavior will put the following code automatically in the head section of your HTML page

```
<script type="text/javascript">
        window.addEvent('domready', function(){ var JTooltips = new Tips($$('.hasTip'), { maxTitleChars: 50, fixed: false}); });
 </script>
```

Now where ever you want the tooltip to appear, place the following code in your page.

```
<span class="hasTip" title="Tooltip Title::Tooltip Description">Hover over here to view your tooltip</span>
```

Notice that in the title tag above is your **Title** and **Description** separated by the **::**characters and anything between the **span** tags may be changed

The following styles are the **default tooltip** styles

```
/* Tooltips */
.tool-tip {
   float: left;
   background: #ffc;
   border: 1px solid #D4D5AA;
   padding: 5px;
   max-width: 200px;
}
 
.tool-title {
   padding: 0;
   margin: 0;
   font-size: 100%;
   font-weight: bold;
   margin-top: -15px;
   padding-top: 15px;
   padding-bottom: 5px;
   background: url(../images/selector-arrow.png) no-repeat;
}
 
.tool-text {
   font-size: 100%;
   margin: 0;
}
```

Override the above styles in your templates stylesheet in order to change the styling of the **tooltip**.

To read more about the **Joomla! tooltip behavior** click here
