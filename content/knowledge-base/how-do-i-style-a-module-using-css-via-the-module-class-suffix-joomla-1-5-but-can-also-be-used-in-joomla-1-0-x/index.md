---
author: "icarnaghan"
title: "How do I style a module using CSS via the Module Class Suffix? Joomla! 1.5 but can also be used in Joomla! 1.0.x?"
date: 2018-04-06
---

If you've downloaded a **Module** and installed in into your **Joomla! site** and you want to add some custom styling to it you may want to use the "**Module Class Suffix**" option located in the **Module Parameter settings**. This Tutorial will direct you step-by-step on how to use the "**Module Class Suffix**" for a **Module**. _**(Basic Knowledge of CSS (Cascading Style Sheets) is required)**_

**STEP 1**

Locate your Template that you are currently using CSS stylesheet. In the **Joomla! Administrator (www.yoursite.com/administrator), select** _**(Extensions->Template Manager)**_ once in the **Template Manager** select the **Radio Button** next to you **DEFAULT template**. Once selected click on the **Edit** button. Once in the next screen click on the **Edit CSS button.** Once in the next screen click on the **Radio Button** next to the **DEFAULT templates stylesheet** to select it and once again click on the **Edit**button. The CSS file will now be editable. At the top of the file add your **CSS class**. It needs  to be specified in a Unique way in order to use it in the **Module Class Suffix**.

View Example Below in Red 

**table.moduletable-test td{ text-transform: uppercase; font-size: 12px; color: #8a4713;**

**}**

- Replace test with your custom name

- Between the {} define the properties for the Class

 

Click on the **SAVE** button to save changes to the file once done editing.

**STEP 2**

Select **Extensions->Module Manager** now the **Module Manager** appears.

![Example 1](images/mm1.jpg "Example 1")

 

**STEP 3**

Now select a **Module** by Clicking on the **Module** name.

![Example 2](images/mm2.jpg "Example 2")

**STEP 4**

Once in the **Module settings** locate the **Module Parameters** setting usually on the right hand site of the Screen. Locate the **Module Class Suffix** setting. Once the setting has been located type in the **CSS** **class** in the text field that you have defined in the **Default Joomla! template CSS** **file** or a predefined one. Some of the common styles are -blank, -dotted, -photo, -dashed, -black, and lots more. **Make sure you include the dash before the style: -blank instead of: blank.** Check Screenshot below (we used class -test). Click on **SAVE** and the style should be applied to the **Module**.

![Example 3](images/mm3.jpg "Example 3")
