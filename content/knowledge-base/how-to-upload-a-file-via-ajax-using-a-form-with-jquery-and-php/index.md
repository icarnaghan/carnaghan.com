---
author: "icarnaghan"
title: "How to upload a file via Ajax using a form with JQuery and PHP"
date: 2018-03-21
---

Click here to download **JQuery** files

**Answer**:

1. Create a new file called **form\_upload.php** 
2. Include **JQuery** and the **JQuery Form Plugin** between the head tags in the **form\_upload.php** file. {codecitation class="brush: html;"} <head> <title>Ajax File Uploader</title>
    
    <script type="text/javascript" src="/jquery-1.3.2.js"></script> <script type="text/javascript" src="/jquery.form.js"></script> </head> {/codecitation}
3. Include the following code between the head tags underneath the **JQuery Form Plugin** include {codecitation class="brush: javascript"} <script type="text/javascript"> <!-- $(document).ready(function() { var options = { target: '#message', //Div tag where content info will be loaded in url:'upload.php', //The php file that handles the file that is uploaded beforeSubmit: function() { $('#uploader').html('<img src="/ajax-loader.gif" border="0" />'); //Including a preloader, it loads into the div tag with id uploader }, success:  function() { //Here code can be included that needs to be performed if Ajax request was successful $('#uploader').html('');
    
    } };
    
    $('#upload').submit(function() { $(this).ajaxSubmit(options); return false; });
    
    }); //--> </script> {/codecitation}
4. Between the body tags we include the actual form and necessary div tags. {codecitation class="brush: html;"} <div id="message"></div> <form name="upload" id="upload" action="#" method="POST" enctype="multipart/form-data"> <table cellpadding="4" cellspacing="4" border="0"> <tr> <td colspan="2"><h1>Upload File via Ajax</h1></td> </tr> <tr> <td class="fieldLabel" nowrap>File:</td> <td nowrap><input type="file" name="fileToUpload" id="fileToUpload" /></td> </tr> <tr> <td nowrap colspan="2"><input type="submit" id="uploadFile" value="Upload File" /></td> </tr>
    
    </table> </form> <div id="uploader"></div> {/codecitation}
5. Create a file called **upload.php** this file will handle all request that are posted via the file upload form. Example of **upload.php** {codecitation class="brush: php;"} echo '<pre>'; print\_r($\_FILES); {/codecitation}
6. The complete code can be obtained below
    
    ```
    <!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
    <html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="en">
    <head>
        <title>Ajax File Uploader</title>
        <script type="text/javascript" src="/jquery-1.3.2.js"></script>
        <script type="text/javascript" src="/jquery.form.js"></script>
        <script type="text/javascript">
        <!--
            $(document).ready(function() {
                var options = {
                target: '#message', //Div tag where content info will be loaded in
                url:'upload.php', //The php file that handles the file that is uploaded
                beforeSubmit: function() {
                    $('#uploader').html('<img src="/ajax-loader.gif" border="0" />'); //Including a preloader, it loads into the div tag with id uploader
                },
                success:  function() {
                    //Here code can be included that needs to be performed if Ajax request was successful
                    $('#uploader').html('');
                }
                };
    
                $('#upload').submit(function() {
                    $(this).ajaxSubmit(options);
                    return false;
                });
            }); 
         //-->
        </script>
    </head>
    <body>
        <div id="message"></div>
        <form name="upload" id="upload" action="#" method="POST" enctype="multipart/form-data">
            <table cellpadding="4" cellspacing="4" border="0">
                <tr>
                    <td colspan="2"><h1>Upload File via Ajax</h1></td>
                </tr>
               <tr>
                    <td class="fieldLabel" nowrap>File:</td>
                    <td nowrap><input type="file" name="fileToUpload" id="fileToUpload" /></td>
                </tr>
                <tr>
                    <td nowrap colspan="2"><input type="submit" id="uploadFile" value="Upload File" /></td>
                </tr>   
            </table>
        </form>
        <div id="uploader"></div>
    </body>
    </html>
    ```
    

For more information on the JQuery Form Plugin visit http://malsup.com/jquery/form/
