---
author: "icarnaghan"
title: "How to Fix the WordPress White Screen of Death"
date: 2016-05-16
categories: 
  - "coding"
---

The dreaded WordPress white screen of death means something has gone wrong and is preventing your website from loading. In most cases, the white screen of death will prevent both the front and back end from loading correctly and all you can see is a blank white screen in your web browser. The white screen of death is often caused by a faulty plugin or theme. In some cases, corrupt files, a database error, or a hosting issue could be the cause of the problem.

## Plugins

Plugins are the most common cause of the white screen of death and should always be checked first. You will need to disable WordPress plugins via FTP. Login to your FTP server and navigate to the **wp-content/plugins** folder. You will see a list of folders for the plugins you have installed. This will include both activated and deactivated plugins. Rename the folders and WordPress will disable the plugins. For example, change the folder **akismet** to **akismet1**.

Go back to WordPress and try loading a page. If your website is now working, then a plugin is causing the problem. If not, you will need to explore other causes of the white screen of death. To find which plugin is causing the problem, you need to rename the plugin folders back to their original names one at a time. After renaming one of the folders, you should check to see if your website loads correctly. If you activate a plugin and WordPress immediately stops working, you have found the guilty plugin.

## Themes

Themes are the next most common reason for the white screen of death. To test your theme, you should follow the same procedure as described for checking plugins. Theme files are located in the **wp-content/themes** folder. Disable your current theme by renaming the folder and WordPress will revert back to the default theme. If your website is now working, then your theme is causing the problem. If your theme is causing the issue, then you can either try and fix the current theme you're using or find a new theme.

## **Hosting**

It may be that your website has simply outgrown your hosting package. Websites that attract a lot of traffic require more resources to run. If your current hosting package can't cope with the amount traffic your website is receiving, then it may be time to upgrade. Before upgrading your hosting, you should try to increase the memory limit to provide WordPress with more memory. Allocating more resources to WordPress should help your website to run smoothly. To increase the memory limit you will need to modify the **wp-config.php** file and add the following line of code:

```
define('WP_MEMORY_LIMIT', '64M');
```

This will increase the memory limit to 64MB which should be sufficient for most websites. You can try increasing the limit even further, but you are limited by your hosting plan. If you reach the maximum resources allowed on your plan, then you should consider an upgrade.

## Updates

WordPress updates could also be causing a problem. If you got the white screen of death after an update, you'll need to roll back to a previous version. You can either install a plugin such as WP Rollback or you can copy the files manually via FTP. If you're going to copy the files via FTP, then you will need to download the version of WordPress that you want to roll back to and upload and overwrite all the files and folders except for the **wp-content** folder. You will also need to edit the **wp-config.php** file and update the database settings.

If your WordPress website is now functioning correctly, you can assume that an update was causing the problem. WordPress updates usually conflict with plugins and themes. Sometimes theme and plugin developers need to update their code so that it works with the latest WordPress updates. You may need to wait until your plugins and themes have been updated before you can update to the latest version of WordPress.

## Database Repair

A corrupt database could also be the cause for the white screen of death. To repair your database, go to phpMyAdmin in your cPanel. On the left sidebar, select your WordPress database. If you aren't sure which one it is, you can check the database name in the **wp-config.php** file. Under your selected database, select all the tables and select "Repair Table" from the dropdown menu at the bottom of the screen. After repairing the tables, check your website to see if it is now working correctly.

Unfortunately, WordPress can sometimes run into problems and the white screen of death can cause everything to stop working. In most cases, plugins and themes are responsible and are usually easy to fix. If you have tried everything possible to get your website back up and running and you're still getting the white screen of death, it may be time to call in a professional.
