---
author: "icarnaghan"
title: "Creating Aliases in Ubuntu"
date: 2018-04-07
---

How to create **Aliases** in **Ubuntu**? If you have a **command** that you run all the time in **Ubuntu** like **pwd** to print your working directory, you can create an alias for that specific command. In otherwords a shorter version for the **pwd** command.

 

1. Open a **Terminal Window** (CLI = Command Line Interface)
2. Type the command **cd** to take you to your home directory.
3. Now you need to edit the **.bashrc** file.
4. To edit the **.bashrc** file, type in the following command: **gedit .bashrc**
5. This will open the **.bashrc** file in **GEdit** for editing.
6. Now we want to assign a **alias** for the **pwd** command. We want to name the **alias**"**p**"
7. Add the following line at the bottom of the **.bashrc** file: **alias p='pwd'**
8. Close **GEdit**.
9. Log out and log in again to make the **alias active**.
10. Type in **p** in the command line and it should give the same results as **pwd**.
