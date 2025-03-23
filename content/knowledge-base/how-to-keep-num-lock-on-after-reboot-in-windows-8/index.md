---
author: "icarnaghan"
title: "How to keep NUM LOCK on after reboot in Windows 8"
date: 2018-03-24
---

1. Press **WINDOWS KEY + R** together, when the Run Window pops-up type in **regedit** and click on **Run
    
    ![Run -> Regedit](images/run-regedit.png "Run -> Regedit")
    
    **
2. In the **Registry Edit windows** that pops-up, navigate to **_HKEY\_USERS->.DEFAULT->CONTROL PANEL->KEYBOARD_** and double click on **InitialKeyboardIndicators** on the right
    
    **![RegEdit - Initialkeyboardindicators](images/regedit-InitialkeyboardIndicators.png "RegEdit - Initialkeyboardindicators")
    
    **
3. Set the **Value data** value to **2** and click **OK**
    
    **![Edit String - RegEdit](images/editstring-regedit.png "Edit String - RegEdit")**
4. Reboot your machine and the **Num Lock** should be on without turning it on mannually.
