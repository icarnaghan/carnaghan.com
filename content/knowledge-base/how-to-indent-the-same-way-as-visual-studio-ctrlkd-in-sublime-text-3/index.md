---
author: "icarnaghan"
title: "How to indent the same way as Visual Studio Ctrl+k+d in Sublime Text 3"
date: 2018-04-07
---

1. Open **Sublime Text 3**
2. Click on **_Preferences -> Key Bindings - User_**
3. Make sure you have the following line:
    
    ```
    [
        { "keys": ["ctrl+k", "ctrl+d"], "command": "reindent", "args": {"single_line": false} }
    ]
    ```
