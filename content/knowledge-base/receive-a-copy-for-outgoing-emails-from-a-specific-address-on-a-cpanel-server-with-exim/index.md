---
author: "icarnaghan"
title: "Receive a copy for Outgoing Emails from a specific address on a CPanel server with Exim"
date: 2018-04-07
---

1. Within **Web Host Manager**, go to **Exim Configuration Manager** then **Advanced Editor**, click on **Save** without changing anything in this section
2. This should create a file named **/etc/exim.conf.local**
3. Edit the above mentioned file and add some configurations to the **@CONFIG@**and **@TRANSPORTSTART@** sections
    
    ```
    @CONFIG@
    system_filter_directory_transport = local_copy_outgoing
    
    ```
    
    ```
    @TRANSPORTSTART@
    local_copy_outgoing:
    driver = appendfile
    delivery_date_add
    envelope_to_add
    return_path_add
    group = cpaneleximfilter
    user = cpaneleximfilter
    mode = 0660
    maildir_format = true
    create_directory = true
    ```
    
4. Next make a copy of **/etc/cpanel\_exim\_system\_filter**
    
    ```
    cp /etc/cpanel_exim_system_filter /etc/cpanel_exim_system_filter_custom
    ```
    
5. Add the following code to the bottom of **/etc/cpanel\_exim\_system\_filter\_custom
    
    **
    
    ```
    if $header_from: contains "test@yourdomain.co.za"
    then
    unseen deliver "copy@recipientdomain.co.za"
    endif
    ```
    
6. Now within **Web Host Manager**, go to **Exim Configuration Manager** and **Advanced Editor** and follow the screenshot below ![](images/vH4QQ6LAzGDizAAAAAElFTkSuQmCC)
7. Click on **Save** and your done
