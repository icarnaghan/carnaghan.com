---
author: "icarnaghan"
title: "Mozilla Thunderbird - Unable to write the email to the mailbox. Make sure the file system allows you write privileges, and you have enough disk space to copy the mailbox"
date: 2018-04-06
---

Although there are many reasons why this error message might appear, one of the reasons is that the mail account giving the error shares the same inbox as another mail account. In this case it could most likely mean that the _**Message Store Type**_ is different for each mail account.

To check the _**message store type**_  click on **Tools->Account Settings

![](images/vKcLAAAAAElFTkSuQmCC)

**

Then click on **Server Settings** under the specified mail accounts and check the **Message Storage Type** for each.

![](images/kOUD0m2FIkgAAAAASUVORK5CYII=)

Should the **Message Storage Types** differ for what ever reason change them to be the same.

Follow the steps below to change the **Message Storage Type** for a email account.

1. Select **Tools->Options
    
    **
2. Click on the **Advanced** Tab and then on **Config Editor
    
    ![](images/9ZY+KcvSAAAAAASUVORK5CYII=)
    
    **
3. Click on **I accept the risk!
    
    ![](images/1DmToAAAAASUVORK5CYII=)**
4. Search for **mail.serverDefaultStoreContractID** and change the **Message Storage Type** to the **Message Storage Type** of the working mail account.
    
    **MBOX** = @mozilla.org/msgstore/berkeleystore;1 **MailDir** = @mozilla.org/msgstore/maildirstore;1
5. Restart Thunderbird.
6. Remove and re-add the working email account.
