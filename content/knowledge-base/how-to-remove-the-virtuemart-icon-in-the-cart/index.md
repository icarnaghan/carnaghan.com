---
author: "icarnaghan"
title: "How to remove the Virtuemart icon in the Cart"
date: 2018-03-25
---

Open the file **components/com\_virtuemart/themes/default/templates/common/minicart.tpl.php**

Comment out or remove lines 7-9

```
 
<a href="http://virtuemart.net/" target="_blank">
 
<img src="<?php echo $mm_action_url ?>components/com_virtuemart/shop_image/ps_image/menu_logo.gif" alt="VirtueMart" width="80" border="0" /></a>
 
<br />
```
