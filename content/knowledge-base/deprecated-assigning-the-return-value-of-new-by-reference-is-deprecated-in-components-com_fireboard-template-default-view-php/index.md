---
author: "icarnaghan"
title: "Deprecated: Assigning the return value of new by reference is deprecated in components/com_fireboard/template/default/view.php"
date: 2018-03-30
---

I get the error _**Deprecated: Assigning the return value of new by reference is deprecated in components/com\_fireboard/template/default/view.php on line 509**_

and

_**Deprecated: Assigning the return value of new by reference is deprecated in components/com\_fireboard/template/default/view.php on line 1037**_

after I've upgraded to **PHP 5.3** within my **Fireboard Joomla! component** when viewing a forum entry.

**NOTE**: The following versions of **Joomla!** and **Fireboard** I had installed when this error occured.

1. Joomla! Version 1.5.22
2. Fireboard Version 1.0.4

Please view my answer for what I did in order to resolve this issue

1. Open the file **components/com\_fireboard/template/default/view.php**
2. Edit line 506 from
    
    ```
    $params =& new mosParameters( '' );
    ```
    
    to
    
    ```
    $params = new mosParameters( '' );
    ```
    
3. Edit line 1037 from
    
    ```
    $params =& new mosParameters( '' );
    ```
    
    to
    
    ```
    $params = new mosParameters( '' );
    ```
    
4. Save the file
5. Refresh your page, and the error message will be gone.
