---
author: "icarnaghan"
title: "How to remove the link 'Ask a question about this product' in VirtueMart 1.1.8"
date: 2018-03-30
---

- Open**components/com\_virtuemart/themes/default/templates/product\_details/flypage.tpl.php**for editing
- On line 43 replace
    
    ```
    <td colspan="2"><?php echo $ask_seller ?></td>
    ```
    
    with
    
    ```
    <td colspan="2">&nbsp;</td>
    ```
    
- Now the link _**'Ask a question about this product'**_ will disappear
