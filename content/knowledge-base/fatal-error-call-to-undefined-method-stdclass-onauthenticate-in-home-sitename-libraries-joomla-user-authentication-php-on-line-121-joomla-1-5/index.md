---
author: "icarnaghan"
title: "Fatal error: Call to undefined method: stdClass->onAuthenticate() in /home/sitename/libraries/joomla/user/authentication.php on line 121 (Joomla! 1.5)"
date: 2018-04-06
---

When trying to log into the **backend** after entering the **username** and **password** and as soon as you click on **login**, I get the following error. **Fatal error: Call to undefined method: stdClass->onAuthenticate() in /home/sitename/libraries/joomla/user/authentication.php on line 121 (Joomla! 1.5)**

**Solution**

Change the file permissions of the plugin folder to at least 755. And try again and the backend should load perfectly

**boss** Friday, 01 October 2010

When trying to log into the administrator page after entering the username and password and as soon as you click on login ..... this error will comes..Fatal error: Call to undefined method stdClass::onAuthenticate() in /home/optisol/public\_html/onlinecourse/libraries/joomla/user/authentication.php on line 121

VOTES:-1

**boss** Friday, 01 October 2010

send the comment to me quickly

VOTES:0

**TechPortal** Friday, 01 October 2010

Did you try changing the permissions of the plugin folder?

VOTES:0

**b** Friday, 01 October 2010

how to find this comment {Did you try changing the permissions of the plugin folder? }

VOTES:0

**Anonymous** Sunday, 03 October 2010

I have the exact same error and chmod on plugins didn\\'t work for me. I even did this to make sure all perms were correct:

find . -type f -exec chmod 644 {} \\\\; find . -type d -exec chmod 755 {} \\\\;

and I put unzipped a fresh copy of joomla on top and that didn\\'t work. Any other ideas on this?

VOTES:0

**TechPortal** Monday, 04 October 2010

Anonymous wrote:

I have the exact same error and chmod on plugins didn\\'t work for me. I even did this to make sure all perms were correct:

find . -type f -exec chmod 644 {} &#92;; find . -type d -exec chmod 755 {} &#92;;

and I put unzipped a fresh copy of joomla on top and that didn\\'t work. Any other ideas on this?

Maybe check the ownership of the folder, chown apache:apache or chmod to 777 for testing purposes to make absulutely sure the permissions aren\\'t the issue

VOTES:1

**Percy** Thursday, 05 April 2012

i have the same problem of the erro while tring to login to my site project so; Where exactly do the File Permisions of plugin folder found? i tried to look for it but i cannot see it.

VOTES:0

**TechPortal** Friday, 13 April 2012

Use a application with the name FileZilla and then FTP to your files. Right click on the Plugin folder and click on Permissions.

VOTES:0
