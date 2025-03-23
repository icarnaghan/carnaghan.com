---
author: "icarnaghan"
title: "How to add a new module position in a Joomla! 1.5 template"
date: 2018-03-30
---

- Open your **template file** where you would like to place the **module position**
-  Add the following code to the template file
    
    ```
    <?php if ($this->countModules('customPosition')) : ?>
    <div id="customPosition"  >
    <jdoc:include type="modules" name="customPosition" style="xhtml"  />
    </div>
    <?php endif; ?>
    ```
    
    **NOTE**: _customPosition_ is the **name/identifier** for the new module position
- Now you need to tell **Joomla!** which module positions are available within the template, to do this open the **templateDetails.xml** file within the root folder of your **template** and add the following code within the <install> namespace
    
    ```
    <positions>
       <position>customPosition</position>
    </positions>
    ```
    
    **NOTE**: You would probably only need to add _**<position>customPosition</position>**_ to the template between the _**<positions> tag**_
