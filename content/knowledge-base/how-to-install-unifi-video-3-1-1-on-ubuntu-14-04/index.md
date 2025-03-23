---
author: "icarnaghan"
title: "How to install UniFi Video 3.1.1 on Ubuntu 14.04"
date: 2018-04-07
---

1. Open the **Terminal Window**
2. Download the **Installation** file using the **wget** command
    
    ```
    wget http://dl.ubnt.com/firmwares/unifi-video/3.1.1/unifi-video_3.1.1~Ubuntu14.04_amd64.deb
    ```
    
3. Install the **deb** package
    
    ```
    sudo dpkg -i unifi-video_3.1.1~Ubuntu14.04_amd64.deb; sudo apt-get install -f
    ```
    
4. Open a new **Browser Window** and type in **https://<IP>:7443** replacing **<IP>** with the **NVR IP address** to initiate the **setup** process.
