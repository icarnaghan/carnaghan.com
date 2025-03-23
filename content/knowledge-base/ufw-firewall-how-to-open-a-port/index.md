---
author: "icarnaghan"
title: "UFW Firewall: How to open a port"
date: 2018-04-07
---

When you would like to grant **SSH access** on a **Ubuntu** machine, you would need to allow access to **port 22**. In order to allow **access** to **port 22** you would need to add a rule to **ufw** to open up access to **port 22**.

To allow access to port 22 you would need to do the following:

1. Open a new Terminal Window
2. Enter the following command:
    
    ```
    sudo ufw allow 22
    ```
    
3. The typical success message will look similar to the below:
    
    ```
    Rules updated
    Rules updated (v6)
    ```
    
     
4. Replace 22 with your **port number** that you would like to grant access to.
