---
author: "icarnaghan"
title: "How to encode a URL in JavaScript"
date: 2018-03-21
---

There are two JavaScript function that you can use to accomplish this

1.  encodeURIComponent()
    
    - Encodes a URI component
    - Encodes special characters
    - The following characters: , / ? : @ & = + $ # are encoded
    
    ```
    var url="http://test.com/index.php?url"+encodeURIComponent(url);
    ```
    
2. encodeURI()
    
    - Encode a URI
    - Encodes special characters but not (except) , / ? : @ & = + $ #
    
    ```
    var url="http://test.com/index.php?url"+encodeURI(url);
    ```
