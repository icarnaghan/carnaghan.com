---
author: "icarnaghan"
title: "How to get the value of a radio button within a radio button group when selected using JQuery"
date: 2018-03-21
---

- Give all the **radio buttons** within a **group** the same name
    
    ```
    <input type="radio" name="RADIOGROUP" value="1" />
    <input type="radio" name="RADIOGROUP" value="2" />
    <input type="radio" name="RADIOGROUP" value="3" />
    <input type="radio" name="RADIOGROUP" value="4" />
    
    ```
    
- Now use the following **JQuery** code to obtain the value for the **selected radio button** within the **Group**
    
    ```
    $("input[name=RADIOGROUP]").change(function(){
            alert($(this).val());
     });
    
    ```
