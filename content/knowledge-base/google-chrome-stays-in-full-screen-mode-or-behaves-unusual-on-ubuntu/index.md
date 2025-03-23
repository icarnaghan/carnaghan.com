---
author: "icarnaghan"
title: "Google Chrome stays in full screen mode or behaves unusual on Ubuntu"
date: 2018-04-07
---

**NOTE:** _Experienced this problem with **Google Chrome 5.0.342.9 beta** on **Ubuntu 9.10**_ **Answer**:

- First make a backup of all you personal settings eg. Bookmarks
- Close **Google Chrome** (_Press the key combination Ctrl+e in order to close Chrome_)
- Open a new **Terminal Window** and type in the following command
    
    ```
    rm -rf ~/.config/google-chrome
    ```
    
    or
    
    ```
    rm -rf /home/YOURNAME/.config/google-chrome
    ```
    
- Start **Google Chrome** and you'll notice that **Chrome** has been reset and problem may be fixed.
