---
author: "icarnaghan"
title: "Allowing visitors to only submit a form once using Chronoforms 3"
date: 2018-03-25
---

1. Click on the **form name** under the **Forms Management** tab and ensure that **Data storage is enabled**
2. Next click on the **Validation Tab**
3. Scroll down to the **Server Side Validation** and set **Enable Server Side Validation**to **yes**
4. In the text area **Server Side Validation Code** add the following code
    
    ```
    <?php
     
    $db =& JFactory::getDBO();
     
    $query = "
     
      SELECT count(*)
     
        FROM `jos_chronoforms_table`
     
        WHERE `text_9` = ".$db->Quote($_POST['text_9']).";
     
      ";
     
    $db->setQuery($query);
     
    if ( $db->loadResult() ) {
     
    return "You've already entered this competition";
     
    }
     
    ?>
    ```
    
    Replace **jos\_chronoforms\_table** with the table name where you are storing the form submission data.
    
    In the code above we validate the user against the **field\_9 column** in the database table **jos\_chronoforms\_table**, if the value entered already exist in**jos\_chronoforms\_table** in the **field\_9** column it means the user has submitted the form.
    
    Our **field\_9** in the above example contains the email address, so if the entered email address exist in the table in means that the user already submitted the form
    
    The global variable **$\_POST\['text\_9'\]** contains the form field **text\_9's** value that the user entered.
    
    You may want to replace **field\_9** with your column to check against.
