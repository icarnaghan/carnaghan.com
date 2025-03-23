---
author: "icarnaghan"
title: "Ext not defined VirtueMart"
date: 2018-03-30
---

I've installed _VirtueMart_ on one of my websites, when I opened the _VirtueMart Control Panel_ in my Joomla! Administration Panel I noticed that when the view is set to _**Simple Layout**_ all the tabs "_Accordion Menu_" are extended and I get the following **JavaScript** error: _**Ext not defined**_ and most functionality that includes **JavaScript** is disabled. When I click on _**Extended Layout**_ the problem is solved.

**Solution**:

To solve this problem we need to disable the _**usefetchscript**_ function that VirtueMart uses

Open the _**/administrator/components/com\_virtuemart/virtuemart.cfg.php**_ file and add the following line

```
$_REQUEST['usefetchscript'] = "0";
```

above the line

```
global $mosConfig_absolute_path,$mosConfig_live_site;
```

and save your changes.

Refresh the **VirtueMart Administration Panel** and the problem will be solved.
