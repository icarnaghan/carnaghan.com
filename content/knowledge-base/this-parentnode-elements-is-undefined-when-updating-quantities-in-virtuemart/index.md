---
author: "icarnaghan"
title: "this.parentNode.elements is undefined when updating Quantities in Virtuemart"
date: 2018-03-25
---

To solve this problem open the following file

**components/com\_virtuemart/js/themes/default/templates/product\_details/includes/quantity\_box\_general.tpl.php**

and in line 46 and 47 remove this code 

```
<input type="button" class="quantity_box_button quantity_box_button_up" onclick="var qty_el = this.parentNode.elements[\'quantity[]\']; var qty = qty_el.value; if( !isNaN( qty )) qty_el.value++;return false;" />
 
<input type="button" class="quantity_box_button quantity_box_button_down" onclick="var qty_el = this.parentNode.elements[\'quantity[]\']; var qty = qty_el.value; if( !isNaN( qty ) && qty > 0 ) qty_el.value--;return false;" />
```

and replace it with this code

```
<input type="button" class="quantity_box_button quantity_box_button_up" onclick="var qty_el = document.getElementById(\'quantity'.$prod_id.'\'); var qty = qty_el.value; if( !isNaN( qty )) qty_el.value++;return false;" />
 
<input type="button" class="quantity_box_button quantity_box_button_down" onclick="var qty_el = document.getElementById(\'quantity'.$prod_id.'\'); var qty = qty_el.value; if( !isNaN( qty ) && qty > 0 ) qty_el.value--;return false;" />
```
