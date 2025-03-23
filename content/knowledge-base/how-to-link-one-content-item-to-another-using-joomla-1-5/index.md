---
author: "icarnaghan"
title: "How to link one content item to another using Joomla! 1.5"
date: 2018-04-06
---

- Open the **Joomla! Administrator backend** section
- Click on **Content->Article Manager
    
    **![Article Manager](images/ac1.png "Article Manager")
- Create a new **Article** Type anything in the article and click on **apply** not **save
    
    **![Apply](images/ac2.png "Apply")
- Highlight a selection of text or images and click on the **link button
    
    **![Insert/edit link](images/ac3.png "Insert/edit link")
- A **dialog box** will appear, within the **Link URL** textfield type in the following
    
    ![View source](images/vista_plana.png "View source")
    
    ```
    index.php?option=com_content&view=article&id=
    ```
    
    ![Dialog Box](images/ac4.png "Dialog Box")
- Type the **article ID** at the end of the string that you wish to link to. eg.
    
    ![View source](images/vista_plana.png "View source")
    
    ```
    index.php?option=com_content&view=article&id=14
    ```
    
- The **article ID** could be obtained by opening the **Article Manager** and on the left hand side where the articles are listed the **article IDs** will be listed.
    
    ![Article ID](images/ac5.png "Article ID")
