---
author: "icarnaghan"
title: "Getting JavaScript errors or no response with Virtue Mart when clicking on Add, Apply or Cancel button"
date: 2018-03-30
---

The error is similar to the below and it has to do with the **readfile** php function.

_Error: invalid regular expression flag v Source File: http://joomla/components/com\_virtuemart/fetchscript.php?gzip=0&subdir\[0\]=/themes/default&file\[0\]=theme.js&subdir\[1\]=/js&file\[1\]=functions.js&subdir\[2\]=/js/admin\_menu/js&file\[2\]=virtuemart\_menu.js&subdir\[3\]=/js/admin\_menu/js&file\[3\]=nifty.js&subdir\[4\]=/js/admin\_menu/js&file\[4\]=fat.js&subdir\[5\]=/js/extjs2&file\[5\]=yui-utilities.js&subdir\[6\]=/js/extjs2&file\[6\]=ext-yui-adapter.js&subdir\[7\]=/js/extjs2&file\[7\]=ext-all.js_

This happens most probably because the System Administrator has disabled the **readmore** function within the **php.ini** file on the server. It's the easiest to get it enabled, but most of the time it's impossible since it has been disabled for security reasons. But luckily there are some work arounds.

- In the file: **/var/www/joomla/components/com\_virtuemart/fetchscript.php** replace line 226
    
    ```
    readfile( $file );
    ```
    
    with
    
    ```
    $contents = file_get_contents( $file );
    echo $contents;
    ```
    
- In the file**: /var/www/joomla/components/com\_virtuemart/show\_image\_in\_imgtag.php** replace lines 148 - 166
    
    ```
    if( file_exists( $fileout ) ) {
      /* We already have a resized image
      * So send the file to the browser */
          switch(strtolower($ext))
            {
                case ".gif":
                    header ("Content-type: image/gif");
                    readfile($fileout);
                    break;
                case ".jpg":
                    header ("Content-type: image/jpeg");
                    readfile($fileout);
                    break;
                case ".png":
                    header ("Content-type: image/png");
                    readfile($fileout);
                    break;
            }
    }
    ```
    
    with
    
    ```
    if( file_exists( $fileout ) ) {
      /* We already have a resized image
      * So send the file to the browser */
          switch(strtolower($ext))
            {
                case ".gif":
                    header ("Content-type: image/gif");
                    $fileout = file_get_contents( $fileout );
                    echo $fileout;
                    break;
                case ".jpg":
                    header ("Content-type: image/jpeg");
                    $fileout = file_get_contents( $fileout );
                    echo $fileout;
                    break;
                case ".png":
                    header ("Content-type: image/png");
                    $fileout = file_get_contents( $fileout );
                    echo $fileout;
                    break;
            }
    }
    
    ```
    
- In the file: **/var/www/joomla/administrator/components/com\_virtuemart/classes/shipping/minixml/classes/doc.inc.php**replace line 322
    
    ```
    readfile($filename);
    ```
    
    with
    
    ```
    $contents = file_get_contents($filename);
    echo $contents;
    
    ```
    

Now try again and the issue should be solved.
