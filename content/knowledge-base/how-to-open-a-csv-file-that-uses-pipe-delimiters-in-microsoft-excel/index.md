---
author: "icarnaghan"
title: "How to open a CSV file that uses Pipe Delimiters in Microsoft Excel"
date: 2018-03-24
---

**CSV** stands for **comma separated file**, sometimes we don't want to use **comma's** in a **CSV** file and decide to rather use a **Pipe Delimiter |** especially in cases where one of the columns contains a **paragraph** with **comma's** in. **Open Office** provides us with a **option** to choose the **Delimiter** when opening **CSV** files, but **MS Excel** does not. But luckily theres a way around this.

**NOTE**: This how-to has been based on **Windows Vista**, but will work on other **Windows versions** as well.

 

- **Microsoft Excel** uses the current **list separator** in the locale settings of **Windows**
- Go to **Control Panel**
    
    ![Control Panel](images/de1.PNG "Control Panel")
- Open **Regional and Language Options**
    
    ![Regional and Language Options](images/de2.PNG "Regional and Language Options")
- Click on **Customize this format...**![Customize this format...](images/de3.PNG "Customize this format...")
- The **Customize Regional Options** window will appear
    
    ![Customize Regional Options](images/de4.PNG "Customize Regional Options")
- Change the **List separator** from **,** _(COMMA DELIMITER)_ to **|** _(PIPE DELIMITER)
    
    _![List separator](images/de5.PNG "List separator")
- Open the **CSV file** with **Pipe Delimiters** again in **MS Excel** and it will open as expected.
