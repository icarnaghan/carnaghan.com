---
author: "icarnaghan"
title: "How to get the Attribute Label of a attribute in a Model using Yii Framework"
date: 2018-03-22
---

1. Use the **getAttributeLabel()** method (available since v1.1.4)
2. Code Example:
    
    ```
    Products::model()->getAttributeLabel('brand_id')
    ```
    
3. The above example gets the attribute label for the brand\_id attribute in the model Products.
