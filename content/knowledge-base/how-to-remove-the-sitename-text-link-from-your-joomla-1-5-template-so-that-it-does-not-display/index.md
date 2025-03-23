---
author: "icarnaghan"
title: "How to remove the sitename text/link from your Joomla! 1.5 template, so that it does not display"
date: 2018-03-30
---

This text usually appears in the header of your webpage.

**NOTE**: Before applying any changes, always remember to take a backup of the previous state.

**Answer**:

1. Click on **Extensions->Template Manager
    
    **![Extensions->Template Manager](images/ex.png "Extensions->Template Manager")
2. The **Template Manager** page will now open, click on the name of the relevant template "_**The template that is selected for your site**_"
3. Click on the **Edit Html** button
    
    ![Edit HTML](images/ex1.png "Edit HTML")
4. Search and Remove for the following line/s
    
    ```
    <a href="<?php echo $baseUrl; ?>/"><?php echo $mainframe->getCfg('sitename') ;?></a>
    ```
    
    or
    
    ```
    <?php echo $mainframe->getCfg('sitename') ;?>
    ```
    
5. Click on the **Save** button
    
    ![Save](images/ex2.png "Save")
6. Refresh your webpage and the **sitename text/link** should be gone. **_NOTE_**: _If the changes to not take effect, try to clear the Joomla! Cache_
