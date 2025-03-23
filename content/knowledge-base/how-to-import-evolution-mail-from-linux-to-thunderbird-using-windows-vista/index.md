---
author: "icarnaghan"
title: "How to import Evolution Mail from Linux to Thunderbird using Windows Vista"
date: 2018-04-06
---

If you were using Evolution Mail using Linux, in our case the Ubuntu distribution and need to switch over to Windows Vista  using Mozilla Thunderbird and need to import your Evolution mailbox to your Thunderbird mailbox.

NOTE: Linux distribution used Ubuntu (May differ from other distributions)

Follow these steps below to import your mail successfully.

**STEP 1**

In Linux, locate the home directory and then the user (usually your name/username). The Evolution mail folder is hidden, so press **CTRL+H** together to view hidden folders.

**STEP 2**

You'll see a folder called **.evolution** 

Now locate the directory below

**.evolution/mail/local/**

NOTE: You might want to copy this directory to a Flash Drive or something similar.

**STEP 3**

Sort the files by size, and you find all your mail folders. Copy the files with only one name and not those who have any other extensions. E.g. **Send** and not **Send.cmeta**, **Send.ibex.index** or **Send.ibex.index.data**

**STEP 4**

Now copy all the files over to the **Thunderbird** directory in **Windows Vista** the directory can be found in the root directory under **USERS\\YOURNAME\\APPDATA\\ROAMING\\THUNDERBIRD\\PROFILES\\xxxxx.default\\Mail\\Local Folders** and all you're old mail will be back when you open Thunderbird.

NOTE: The **.evolution** folder and the **AppData** folder might be hidden folders
