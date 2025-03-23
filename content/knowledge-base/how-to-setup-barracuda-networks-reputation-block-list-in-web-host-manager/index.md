---
author: "icarnaghan"
title: "How to setup Barracuda Networks Reputation Block List in Web Host Manager"
date: 2018-04-07
---

1. Login to WHM using your **root** username and password.
2. Search and open **Exim Configuration Manager
    
    **![](images/wdEbxBJRFZ5PAAAAABJRU5ErkJggg==)
3. Click on the **RBLs** tab under the **Basic Editor** tab
    
    ![](images/wQeSGxbQZY0AAAAASUVORK5CYII=)
4. Click on **Manage**
    
    ![](images/3y3S09gAf8HsAfQgT2ADuwBdGAPoAN7AB3YA+jAHkDnL1PapOYw2rIfAAAAAElFTkSuQmCC)
5. Add Barracuda RBL under the **Add a new RBL** Section
    - **Rbl Name =** Barracuda
    - **Rbl Info URL** \= http://www.barracudacentral.org/rbl/removal-request
    - **Dns List** \= b.barracudacentral.org
        
        ![](images/B96UXZw7TTlJgAAAABJRU5ErkJggg==)
6. Click on **Add
    
    **
7. Return to the **Exim Configuration Manager**, and under the **Basic Editor->RBLs** tab switch the **Custom RBL: Barracuda** Rbl **On
    
    ![](images/gAAAKr9HzDgNNvNKADIAAAAAElFTkSuQmCC)**
