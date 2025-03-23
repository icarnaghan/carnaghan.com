---
author: "icarnaghan"
title: "How to change your MAC Address in Linux"
date: 2018-04-07
---

**NOTE**: In this example we will change the **MAC address** for the **eth0** **interface**

1. Open your **Command Line Interface**
2. Now we are going to **shutdown** the **eth0** **Interface** using the command below
    
    ```
    ifconfig eth0 down
    ```
    
3. Now we change the **Hardware Address** for the **eth0 interface**
    
    ```
    ifconfig eth0 hw ether 00:1d:72:dd:00:6f
    ```
    
4. Now we activate the **eth0** **interface** again
    
    ```
    ifconfig eth0 up
    ```
