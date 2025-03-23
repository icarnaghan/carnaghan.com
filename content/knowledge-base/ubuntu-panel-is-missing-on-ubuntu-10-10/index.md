---
author: "icarnaghan"
title: "Ubuntu Panel is missing on Ubuntu 10.10"
date: 2018-04-07
---

- Open the command line, to do this **right click** on the **Desktop** and select **Create Launcher**... In the **Command** text field type in **gnome-terminal** and in the **Name**text field **Terminal** click **OK
    
    **![Create Launcher](images/createlauncher.png "Create Launcher")
    
- A new shortcut called **Terminal** will appear, double click on it to **Open** a new **Terminal** **window** ![Terminal](images/Terminal.png "Terminal")
- Type the following command
    
    ```
    killall gnome-panel
    ```
    
- Create another Launcher as in step one type in the command text box **gnome-panel** give it a name, and then run the launcher and the **Gnome Panel** will be back.
    
    ![Gnome Panel](images/Gnome%20Panel.png "Gnome Panel")

**NOTE**: If the Panel disappears again when re-booting try to install gnome-panel

```
sudo apt-get install gnome-panel
```
