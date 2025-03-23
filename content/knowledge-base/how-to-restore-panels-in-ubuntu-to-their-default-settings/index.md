---
author: "icarnaghan"
title: "How to restore panels in Ubuntu to their default settings"
date: 2018-04-07
---

How to **restore** **panels** in **Ubuntu** to their **default settings** after maybe **deleting** the **Panels** or accidentally removed an **icon** or something? You could always add the **Panels/Icons** one by one, but that's time consuming. The quickest answer is below.

**STEP 1**

Start a **Terminal** **session**. To do this press **ALT+F2** together. The **Run Application**window should appear.Type in "**gnome-terminal**" click on **Show list of known applications** and select **Terminal** and click on run.

![Gnome Terminal](images/run_app_gnome_term.png "Gnome Terminal")

 

**STEP 2**

The **Terminal window** should be open now. Enter the following command "**gconftool --recursive-unset /apps/panel**" and hit Enter.

**STEP 3**

After the previous **command** **executed** successfully type in the following command "**pkill gnome-panel**" and hit Enter.

**STEP 4**

All **Panels** top and bottom should appear. Or the **missing** **panel** will appear again. **Customize** them to you're previous **settings**.

 

**NOTE**: Has been tested on **Ubuntu 7.10 Gutsy Gibbon**, **Ubuntu Hardy Heron 8.04**and **Ubuntu Jaunty 9.04**
