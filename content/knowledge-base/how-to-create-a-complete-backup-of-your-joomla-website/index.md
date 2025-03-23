---
author: "icarnaghan"
title: "How to create a complete Backup of your Joomla! website"
date: 2018-04-06
---

To **Backup** your **Joomla! Website** you need to have your **FTP** details ready. You need to create a complete **Backup** of all your **Joomla! Files** and also a **Backup** of your **mySql database** witch keeps **important** information for your site.

**STEP 1**

Use your **FTP client** to log in to your **account** using your **FTP details** to access your **Joomla!** files

**STEP 2**

**Navigate** to your **Joomla! root folder**, download the whole folder to your local **Hard drive** on your PC. Or you may want to **zip/compress** the folder and then **download** it.

**STEP 3**

You need to make a **Backup** of the **mySql Database** for your site. In order to do that you need to access **phpMyAdmin** or **mySql Administrator**. **phpMyAdmin** **interface** should be available in the **cPanel** for your account.

Look for the **Icon "phpMyAdmin"** and click on it. **phpMyAdmin** interface should now open.

**STEP 4**

Select your sites **mySql Database** on the left hand site of the screen in the **Drop down** box. Click on the **Export** button. **Highlight all the Tables**. Check the checkbox **Save as file.** Click on **Go** and your **Database** will be downloaded with extension **\*.sql**.

To **import** the **mySql** file again, in **phpMyAdmin** click on the **import** button, if the **import** button is missing, click on the **SQL** button. Choose the **sql** file that you wish to **import** and **upload** it and the **mySql Backup** should be **restored**.
