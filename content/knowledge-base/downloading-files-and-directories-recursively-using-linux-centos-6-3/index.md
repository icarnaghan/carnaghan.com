---
author: "icarnaghan"
title: "Downloading Files and Directories recursively using Linux Centos 6.3"
date: 2018-04-07
---

1. Install **ncftp** using **yum**
    
    ```
    sudo yum install ncftp
    ```
    
2. Execute the following command, just replace details with the relevant ones
    
    ```
    ncftpget –R –v –u ftpusername ftpserver /copying/to/directory /copying/from/directory
    ```
    
3. **\-R** = Recursive mode; copy whole directory trees **\-v** = Use progress meters **\-u** = FTP username **\-ftpusername** = Replace with your FTP username **\-ftpserver** = Add your server in here **\-/copying/to/directory** - Directory to copy to **\-/copying/from/directory** - Directory to copy from
