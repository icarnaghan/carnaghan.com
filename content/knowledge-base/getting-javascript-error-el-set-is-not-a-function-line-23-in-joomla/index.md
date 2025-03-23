---
author: "icarnaghan"
title: "Getting JavaScript error el.set is not a function Line: 23 in Joomla!"
date: 2018-03-30
---

I've noticed this error when I installed **VirtueMart** and in the checkout process where it asks if you are a **returning visitor** or **new user** I noticed that the radio buttons did not work. This error occurs since **Joomla!** uses **mootools** and I used **JQuery** in my template. Thus causing the two to conflict since both **mootools** and **JQuery** make use of the _**$-function**_. Please check the answer to see how you will be able to solve this issue.

**Answer**:

1. Add the following code after the inclusion of the **JQuery** library.
    
    ```
    <script type="text/javascript">
       jQuery.noConflict();
     </script>
    ```
    
    eg.
    
    ```
    <script type="text/javascript" src="<?=JURI::root().'/scripts/jquery-latest.pack.js'?>"></script>
    <script type="text/javascript">
       jQuery.noConflict();
     </script>
    ```
    
    **jQuery.noConflict();** overrides JQuery's **_$-function_**
2. Now replace all **$ instances** in your code with **jQuery** eg. _**$("#test")** will become_ _**jQuery("#test")**_
3. Refresh your page and the error message should be gone.
