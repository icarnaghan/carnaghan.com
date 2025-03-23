---
author: "icarnaghan"
title: "How to adjust the width of a HTML combobox (Drop down box or Select box)"
date: 2018-03-22
---

- You can use **external CSS (Cascading Style Sheets)** or **Inline Styles**. **NOTE**: External CSS stylesheets are best to use.
- Example using inline styles.
    
    ```
    <select style="width:200px;">
        <option>Option 1</option>
        <option>Option 2</option>
        <option>Option 3</option>
    </select>
    ```
    
- Example using external CSS
    
    **HTML**
    
    ```
    <select class="dropdown">
        <option>Option 1</option>
        <option>Option 2</option>
        <option>Option 3</option>
    </select>
    ```
    
    **CSS**
    
    ```
    .dropdown{
        width: 200px;
    }
    ```
