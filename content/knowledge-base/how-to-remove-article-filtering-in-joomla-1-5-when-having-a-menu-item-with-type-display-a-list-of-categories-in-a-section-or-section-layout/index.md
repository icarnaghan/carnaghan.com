---
author: "icarnaghan"
title: "How to remove Article Filtering in Joomla! 1.5.* when having a menu item with type \"Display a list of Categories in a Section\" or \"Section Layout\""
date: 2018-04-06
---

If you have a menu item with type "**Category List**" then it's under the **Basic Parameters** options. More on this click here

Unfortunately there isn't an easy option for this yet in type "**Section Layout**". To remove the **Article Filtering** option you need to do some code modifications.

1. Locate the following file**components\\com\_content\\views\\category\\tmpl\\default\_items.php**
2. Replace the following line **<?php if ($this->params->get('filter') || $this->params->get('show\_pagination\_limit')) : ?>** with **<?php if (!$this->params->get('filter') || !$this->params->get('show\_pagination\_limit')) : ?>** it should be on line 16
3. Save the file
4. Reload the page and the problem should be solved.

**NOTE**: Maybe in future this will be possible via the Joomla! Administrator backend. When article was published our current Joomla! version was 1.5.10
