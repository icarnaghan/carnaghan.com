---
author: "icarnaghan"
title: "How to install Flash Player in Fedora Core 15 32bit so that the Flash Plugin will work in your Browser"
date: 2018-04-07
---

1. Switch to **root**
    
    ```
    su
    ```
    
2. Add the neccesary **software sources** to the _**yum**_ **repository**
    
    ```
    rpm -ivh http://linuxdownload.adobe.com/adobe-release/adobe-release-i386-1.0-1.noarch.rpm
     
    rpm --import /etc/pki/rpm-gpg/RPM-GPG-KEY-adobe-linux
    ```
    
3. Update all _**yum**_ packages
    
    ```
    yum update
    ```
    
4. Install the **Flash Plugin**
    
    ```
    yum install flash-plugin
    ```
    
5. Restart **Firefox** or your **default browser** and the **Flash Player** should now work on **Fedora Core 15 32bit**
