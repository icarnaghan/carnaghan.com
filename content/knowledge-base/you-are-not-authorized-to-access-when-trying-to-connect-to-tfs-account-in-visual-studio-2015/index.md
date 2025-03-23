---
author: "icarnaghan"
title: "You are not authorized to access when trying to connect to TFS account in Visual Studio 2015"
date: 2018-09-02
---

To solve this problem you have to clean the cache folder on your machine.

1. Press **Win + R** together to open the **Run** window
    
    ![](images/8HPHeJElWXclUAAAAASUVORK5CYII=)
2. Type in **%UserProfile%\\AppData\\Local** and click on **OK
    
    ![](images/8PDSaocAAAAASUVORK5CYII=)
    
    **
3. Navigate to the **Microsoft\\Team Foundation\\6.0\\Cache** folder and delete all contents
    
    ![](images/36c3ggIQZaQAAAABJRU5ErkJggg==)
4. Restart Visual Studio and Re-Open your solution.
5. The error message will disappear and all should be working again.
    
    ![](images/5vkEkveIFXZAAAAAElFTkSuQmCC)
