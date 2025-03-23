---
author: "icarnaghan"
title: "Getting error \"File type not supported\" when trying to upload a file in Joomla! via Media Manager"
date: 2018-03-30
---

**Joomla! 1.0**

- In order to apply this solution, you need to have modifying access to your **Joomla! 1.0** core files
- Locate the following file within your **Joomla! installation** and open it in a text editor. **FILE**: _/administrator/components/com\_media/admin.media.php_
- Round about **lines 170 and 200** you'll find something like:
    
    ```
     
    'bmp',
    'csv',
    'doc',
    'epg',
    'gif',
    'ico',
    'jpg',
    'odg',
    'odp',
    'ods',
    'odt',
    'pdf',
    'png',
    ```
    
    Append the **additional file extension** that you wish to be able for uploading via **Media Manage**r eg '_ogg_'
- The file should look like the below now
    
    ```
     'bmp',
     'csv',
     'doc',
     'epg',
     'gif',
     'ico',
     'jpg',
     'odg',
     'odp',
     'ods',
     'odt',
     'pdf',
     'png',
    'ogg',
    
    ```
    
- **Save** the **file** and try again

**Joomla! 1.5**

- On **Joomla! 1.5** it's a lot easier than on **Joomla! 1.0**
- In the **Administration Panel (**_www.yourjoomlasite.com/administrator)_ go to **Global Configuration**.
- Click on the **System Tab**
- **And the ogg (_or any additional file extensio_n) to the list.**
- **Click on SAVE**
- **And you will be able to upload that specific file type from now on forward.**

![Media Settings](images/mmt.png "Media Settings")

**Anonymous** Wednesday, 16 June 2010

I tried this one in joomla 1.5, but I\\'m still unable to upload mp3 files.

what are other possible conflicts?

thanks much!

VOTES:1

**TechPortal** Wednesday, 16 June 2010

Fortunately there is another solution.

1) Set **CHECK MIME TYPES** and **RESTRICT UPLOADS** to NO within Media Settings in the Configuration.

2) In the p**hp.ini** file _(if you have access to this)_ check if ;

**upload\_max\_filesize** is set to a bigger size than the file you are uploading and also the **post\_max\_size** file size. To locate your **php.ini** file go to the Joomla administration backend and click on help->system info->php information. Around the 6th row, you\\'ll find the path to php.ini. When you need to make a change to php.ini you need to restart apache for changes to take effect.

VOTES:0

**Kayhla** Monday, 13 February 2012

Hi, Ive added \\".exe\\" files to be supported by my joomla website but i still get this error:

\\" JFile::read: Unable to open file: \\'\\' Warning: Failed to move file! Error. Unable to upload file. \\" ive even tried it in a zip folder but i get this error: \\"This file type is not supported.\\"

I need help!

Thank you in advance

VOTES:0

**Kayhla** Monday, 13 February 2012

hello, do not worry i fixed the problem myself, i just uploaded the .exe file with an ftp client :)

VOTES:0

**TechPortal** Monday, 13 February 2012

Please also see that the images folder is writable, in the Joomla! backend you can run a check to see if all neccessary folders are writable

VOTES:0

**AVINASH** Friday, 03 August 2012

still pdf file is not uploading ...plzz help me iam making an ebook site in joomla 1.5....

VOTES:0
