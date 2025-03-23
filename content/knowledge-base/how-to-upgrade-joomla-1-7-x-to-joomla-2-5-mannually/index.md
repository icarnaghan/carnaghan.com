---
author: "icarnaghan"
title: "How to upgrade Joomla! 1.7.x to Joomla! 2.5 mannually"
date: 2018-03-25
---

1. Backup your existing **Joomla! 1.7.x installation** and also your existing **Joomla! 1.7.x database**
2. Download the 2.5.0 update package and not the installation package from here
3. Extract the Update Package to your local machine and upload to your server overwriting existing files using FTP
4. Now we need to delete some files and directories by opening the file _**administrator/components/com\_admin/script.php**_ from the **Upgrade Package**
5. The files and folders are listed towards the end of file
    
    ```
    		$files = array(
     
    		            '/includes/version.php',
     
    		            '/installation/sql/mysql/joomla_update_170to171.sql',
     
    		            '/installation/sql/mysql/joomla_update_172to173.sql',
     
    		            '/installation/sql/mysql/joomla_update_17ga.sql',
     
    		            '/libraries/joomla/application/applicationexception.php',
     
    		            '/libraries/joomla/client/http.php',
     
    		            '/libraries/joomla/filter/filterinput.php',
     
    		            '/libraries/joomla/filter/filteroutput.php',
     
    		            '/libraries/joomla/form/formfield.php',
     
    		            '/libraries/joomla/form/formrule.php',
     
    		            '/libraries/joomla/utilities/garbagecron.txt',
     
    		            '/libraries/phpmailer/language/phpmailer.lang-en.php',
     
    		            '/media/system/css/modal_msie.css',
     
    		            '/media/system/images/modal/closebox.gif',
     
    		        );
     
     
     
    		        // TODO There is an issue while deleting folders using the ftp mode
     
    		        $folders = array(
     
    		            '/libraries/joomlacms',
     
    		            '/media/editors/tinymce/jscripts/tiny_mce/plugins/media/img',
     
    		            '/media/plg_highlight',
     
    		            '/media/mod_finder_status',
     
    		        );
    ```
    
6. Delete all these files mannually using FTP
7. Now we need to update the database by executing a series of sql queries that can be found in the following location: _**administrator/components/com\_admin/sql/updates/mysql**_
8. Before we begin met the execution of the mysql files you need to begin with the file that contains your Joomla! version number and work your way up to the very last Joomla! 2.5.x file, so if you have Joomla! 1.7.3 installed you would start with **1.7.3-2011-10-15.sql** and end with **2.5.3-2012-03-13.sql**
9. Run the queries in phpMyAdmin or any other MySql program, but before running, you will need to open each file and replace the # with the relevant prefix of your database eg. _**ALTER TABLE \`#\_\_banners\`**_ would become _**ALTER TABLE \`mypre\_banners\`**_
10. After all the queries have been performed, everything should be up to date and your Joomla! installation will be the latest
