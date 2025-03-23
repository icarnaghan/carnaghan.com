---
author: "icarnaghan"
title: "How to change the Timezone in CentOS 6"
date: 2018-04-07
---

1. The **timezone** that's active on your system is stored in the file _**/etc/localtime**_
2. First make a backup of the existing **localtime** file
    
    ```
    mv /etc/localtime /etc/locatime.backup
    ```
    
3. Now we create a link so that the timezone auto updates when updates come through
    
    ```
    ln -s /usr/share/zoneinfo/Africa/Johannesburg /etc/localtime
    ```
    
4. In the above change **Africa/Johannesburg** to the appropriate timezone you need to use
5. To test this change run the following command and see if the timezone updated.
    
    ```
    date
    ```
