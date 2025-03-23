---
author: "icarnaghan"
title: "How to Embed CSS into a View using the Yii Framework 1.1"
date: 2018-03-22
---

1. This can be done using the registerCss() method of the CClientScript class. CClientScript manages **JavaScript** and **CSS** **stylesheets** for views.  registerCss()registers a piece of CSS code.
2. Place code similar to the example code below in your **View**
    
    ```
    Yii::app()->clientScript->registerCss('customCSS',<<<CSS
       li {
        font-weight: normal;
       }
    CSS
    );
    
    ```
    
3. In the code above the first parameter is a string and ID that uniquely identifies this piece of **CSS** code. The second Parameter contains the **CSS** code.
4. This code will automatically embed **CSS** into your webpage using your **VIEW**.
