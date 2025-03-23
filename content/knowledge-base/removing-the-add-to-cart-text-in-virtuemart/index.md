---
author: "icarnaghan"
title: "Removing the Add To Cart text in VirtueMart"
date: 2018-03-25
---

Locate the following file **/administrator/components/com\_virtuemart/languages/common/english.php**

And replace

```
'PHPSHOP_CART_ADD_TO' => 'Add to Cart',
```

with

```
'PHPSHOP_CART_ADD_TO' => '',
```

And the text will disappear.
