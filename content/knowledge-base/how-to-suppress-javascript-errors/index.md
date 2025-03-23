---
author: "icarnaghan"
title: "How to suppress JavaScript errors"
date: 2018-03-21
---

1. Create a JavaScript function called **suppressJS()**
    
    ```
    function suppressJS(){return true;}
    ```
    
2. Then within the head tags add the following code
    
    ```
    window.onerror=suppressJS;
    ```
    
3. Your complete code will look like this
    
    ```
    <script type="text/javascript">
     
    <!--
     
    function suppressJS(){return true;}
     
    window.onerror=suppressJS;
     
    //-->
     
    </script>
    ```
