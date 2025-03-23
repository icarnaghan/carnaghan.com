---
author: "icarnaghan"
title: "How to delete a file when getting the error \"Error Deleting File or Folder"
date: 2018-03-24
---

![Error Deleting File or Folder](images/error1.png "Error Deleting File or Folder")

1. The solution is to rename the file in a DOS readable format.
2. Open **Windows Explorer**
3. Locate the File
4. **Right click** in the **File** and click on **Rename**
5. **Rename** the file to a short name eg. file
6. Open up **Command Prompt** by clicking on **"START->PROGRAMS->ACCESSORIES->COMMAND PROMPT"**
7. **Locate the file by using the DOS cd command eg.  cd directory**
8. **Once in the directory of where the file is type in the following command**
    
    ```
    del FILENAME
    ```
    
    **Replace FILENAME with your file**
9. Hit Enter
10. The file should now be gone
