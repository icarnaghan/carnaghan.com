---
author: "icarnaghan"
title: "How to resume CUPS printer in Linux via the Command Line"
date: 2018-04-07
---

1. Find the printer to resume
    
    ```
    lpstat -p
    ```
    
2. After entering the command above you should see a similar message as below
    
    ```
    printer HP_LaserJet_P2015 disabled since Wed 25 Sep 2013 09:35:59 AM SAST -
            /usr/lib/cups/backend/hp failed
    printer HP_LaserJet_P2015_Series is idle.  enabled since Wed 05 Dec 2012 08:16:07 PM SAST
    
    ```
    
3. Enable the printer, replace printer name with your printer
    
    ```
    cupsenable HP_LaserJet_P2015
    ```
    
4. To verify if the printer has been enabled enter the lpstat -p command again
    
    ```
    lpstat -p
    ```
    
    Now you should see similar message as below indicating that the printer has been enabled
    
    ```
    printer HP_LaserJet_P2015 now printing HP_LaserJet_P2015-367.  enabled since Wed 25 Sep 2013 09:42:09 AM SAST
    ```
