---
author: "icarnaghan"
title: "How to check if a Email address exist or not using the command line"
date: 2018-04-06
---

- In this example we will test for the Email address **test212@gmail.com**, replace the **gmail Email address** with the **email address** you want to test
- Open the **command line/command promt** and type in the following command
    
    ```
    nslookup -type=mx gmail.com
    ```
    
    This command will list the **MX records** of the **gmail domain** eg.
    
    ```
    Server:        10.0.2.2
     
    Address:    10.0.2.2#53
    
     
    Non-authoritative answer:
     
    gmail.com    mail exchanger = 5 gmail-smtp-in.l.google.com.
     
    gmail.com    mail exchanger = 10 alt1.gmail-smtp-in.l.google.com.
     
    gmail.com    mail exchanger = 20 alt2.gmail-smtp-in.l.google.com.
     
    gmail.com    mail exchanger = 30 alt3.gmail-smtp-in.l.google.com.
     
    gmail.com    mail exchanger = 40 alt4.gmail-smtp-in.l.google.com.
     
     
    Authoritative answers can be found from:
     
    alt1.gmail-smtp-in.l.google.com    internet address = 74.125.39.27
     
    alt3.gmail-smtp-in.l.google.com    internet address = 74.125.65.27
     
    alt4.gmail-smtp-in.l.google.com    internet address = 74.125.91.27
     
    alt2.gmail-smtp-in.l.google.com    internet address = 209.85.225.27
     
    gmail-smtp-in.l.google.com    internet address = 209.85.227.27
    ```
    
- Select one of the **servers** listed in the **list of MX records** and pretend to **send a message** to that **server** from your **local machine**
    - Connect to the **server** via **telnet**
        
        ```
        telnet alt1.gmail-smtp-in.l.google.com 25
        ```
        
    - Type in the **HELO** command
        
        ```
        HELO
        ```
        
    - Identify yourself using any **email address** eg. **test@test.com**
        
        ```
        mail from:<test@test.com>
        ```
        
    - Type in the **email address** that you wish to **verify**
        
        ```
        rcpt to:<test212@gmail.com>
        ```
        
- After the last command entered, the server will respond with a **message** whether the **email address** **exist/is valid** or **not** e.g.
    
    ```
    250 2.1.5 OK o15si4900954fal.31 //For success
    ```
    
    and
    
    ```
    The email account that you tried to reach does not exist. //Failure
    ```
