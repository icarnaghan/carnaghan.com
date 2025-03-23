---
author: "icarnaghan"
title: "PHP Script that deletes files within a remote directory via FTP older than a given amount of days"
date: 2018-03-22
---

The following PHP script lets you connect to a remote location via PHP's FTP functionality and delete all files older than a certain amount of given days in that directory, it also provides functionality to list files that should be ignored in a array, these files listed in the array won't be deleted even if they are older than the given days.

This script can be used together with a cron job, to automate a process. For example if you have a directory where you store automated backups via FTP and don't have the time to delete old backups, this script can help to automate the process given that you only have FTP access to the directory 

```
$host = "backups.mydomain.com"; //Replace with your host
 
$username = "myUsername"; //Replace with your username
 
$password = "myPassword"; //Replace with your password
 
$mode = "passive"; //Leave blank to go to active mode
 
$dir = "/"; //Put the name of the directory in here where you want to loop through files, put / for root directory
 
$daysOld = '2'; //Enter the age of files in days, if a file should be deleted that's older than 2 days enter 2
 
$filesToSkip = array('.','..','.ftpquota'); //Contains the files that the script needs to skip if it comes accross them
 
$notificationEmail = 'notifyt@mydomain.com'; //The email address to send a notification when file fails to delete
 
//FTP session starting
 
$connection = ftp_connect($host);
 
$login = ftp_login($connection,$username,$password);
     
 
if(!$connection || !$login){
 
    die('Connection attempt failed!');
 
}
 
 
if($mode == 'passive'){
 
    //Switching to passive mode
 
    ftp_pasv($connection,TRUE);
 
}else{
 
    ftp_pasv($connection,FALSE);
 
}
 
 
//Calcuting the datetime of todays day minus the amount of 2days entered
 
$dateToCompare = date('Y-m-d',  strtotime('-'.$daysOld.' days',time()));
 
 
//Looping through the contents of the provided directory
 
 $files = ftp_nlist($connection,$dir); //ftp_rawlist — Returns a detailed list of files in the given directory
 
 foreach($files as $file){
 
     //Check if the file is in the list of files to skip, if it is we continue the loop
 
     if(in_array($file, $filesToSkip)){
 
         continue;
 
     }
 
 
     $modTime = ftp_mdtm($connection, $file);
 
     if(strtotime($dateToCompare) >= $modTime){
 
         if(!ftp_delete($connection,$file)){ //Deleting the file that needs to be deleted
 
             //If the file fails to delete we send a mail to the administrator
 
             mail($notificationEmail, 'FAILED TO DELETE FILE', 'FAILED TO DELETE FILE: '.$file);
 
         }
 
     }
 
 }
```
