---
author: "icarnaghan"
title: "How to set your default editor in Linux"
date: 2018-04-07
---

1. Edit the **.bash\_profile** file in your home directory
    
    ```
    vi ~/.bash_profile
    ```
    
2. Add the following lines to your **.bash\_profile** file
    
    ```
    export VISUAL=vim
    export EDITOR="$VISUAL"
    ```
    
    _**Note:** Replace **vim** with any other preferred editor such as_ **_nano
    
    _**
3. Logout and login again for changes to take effect.
4. If you want the changes to come into play immediately, execute the following command
    
    ```
    . ~/.bash_profile
    ```
