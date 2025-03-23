---
author: "icarnaghan"
title: "Can't delete mail in my Trash folder in Evolution mail, get error \"Summary and Folder mismatch\""
date: 2018-04-06
---

- First create a **backup** of your **mail** using **Evolution** by clicking on **File->Backup Settings** _"This step is vitally important to prevent data loss"_
- By using your **file browser** browse to the following directory**/home/YOURUSERNAME/.evolution/mail/local**
- Once in the **local** folder delete all files with the following extensions. _**.index .cmeta .ev-summary
    
    **_Very important to not delete the files with the **.data extension**
- Restart **Evolution**
- **Evolution** will now attempt to **re-create** all **indexes**
- You should be able to delete the mails in the **trash** folder
