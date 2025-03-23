---
author: "icarnaghan"
title: "Setting the File permissions in Joomla!"
date: 2018-04-06
---

Joomla! is a great content management system and to keep it great we need to make sure that it is secure against Hackers etc. One of the most important things to check to make your Joomla! installation as secure as possible is to make your files and folders as secure as possible. You can start of by setting the file permissions. And of course please ensure that you always have a backup of your Database and Core Joomla! files.

**STEP 1**

Once your site is setup and all the necessary components, modules and plug-ins are installed and files uploaded and you are happy with the site you need to set the permissions on all your directories and sub-directories to **CHMOD 755.** After you changed the directory permissions your directories should be save.

**STEP 2**

After you set the directory permissions you need to set all your Joomla! files to **CHMOD 644** to make your files secure.

**STEP 3**

Make sure that the **Configuration.php** file permissions are set to **CHMOD 644**, **Configuration.php** file is one of the most important files in Joomla! it contains all the details about your current Joomla! setup.

**STEP 4**

The latest Joomla! release includes an updated version of the **.htaccess** file witch reduces the risk of your Joomla! site being hacked. Transfer the **.htaccess** file to your server and set the **.htaccess** file permissions to **CHMOD 644**.
