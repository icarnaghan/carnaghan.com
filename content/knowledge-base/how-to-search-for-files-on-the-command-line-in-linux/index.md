---
author: "icarnaghan"
title: "How to search for files on the command line in Linux"
date: 2018-04-07
---

- By using the _**find**_ command we can _search for files and directories_ using the command line. The _**find**_ command uses a raw search to find files and directories.
- The usage is find \[PATH\] \[OPTIONS\]\[SEARCH CRITERIA\]
    
    Example:
    
    ```
    find /home/ -name test
    ```
    
    The example above finds all files/directories within the home directory that contain the word _**test**_
- Below are different common options that can be used together with the _**find**_ command namely:
    - **\-name** = Find files with the specified name _(see example above)_
    - **\-user** \= Finds files owned by the specified user
    - **\-size** \= Finds files larger than the size specified
    - **\-mtime** **n** = File's data was last modified n\*24 hours ago.
- To read more about the _**find**_ command use the **_man_** command
    
    ```
    man find
    ```
