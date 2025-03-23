---
author: "icarnaghan"
title: "How to get Rid of Inline Attachments in Apple Mail"
date: 2018-04-06
---

This can be done via the **Terminal**

1. Close **Apple Mail**
2. Open the **Terminal** via _**Applications -> Terminal**_
3. Execute the following command from the **Terminal Window**
    
    ```
    defaults write com.apple.mail DisableInlineAttachmentViewing -bool yes
    ```
    
4. Restart **Apple Mail** and the images won't appear inline anymore
