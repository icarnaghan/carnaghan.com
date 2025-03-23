---
author: "icarnaghan"
title: "How to get the 60GB Cell C Speed Stick MF668 working on Ubuntu 11.04"
date: 2018-04-07
---

1. Open a new **Terminal Window**
2. Type in **lsusb** ( _**lsusb** is a utility for displaying information about USB buses in the system and the devices connected to them._ )
3. A list of **USB buses** in the **System** will appear, the **Cell C** **device** will be listed as
    
    ```
    Bus 002 Device 007: ID 19d2:1224 ONDA Communication S.p.A.
    ```
    
4. Install **usb-modeswitch**, **usb-modeswitch-data** and **libusb-1.0-0** via the **Command Line**, the code below can be copied and pasted to install the three packages
    
    ```
    sudo apt-get install usb-modeswitch usb-modeswitch-data libusb-1.0-0
    ```
    
5. After the installation you will need to edit the **usb\_modeswitch.conf** file by executing the following command in order to edit the file
    
    ```
    sudo gedit /etc/usb_modeswitch.conf
    ```
    
6. Append the following code to the **usb\_modeswitch.conf** file
    
    ```
     
    DefaultVendor=  0x19d2
     
    DefaultProduct= 0x1224
     
    TargetVendor=    0x19d2
     
    TargetProduct=0x0017
     
     
    MessageContent="55534243123456782000000080000c85010101180101010101000000000000"
    ```
    
7. Save and close
8. Run the command below in order to detect the new device
    
    ```
    sudo usb_modeswitch -c /etc/usb_modeswitch.conf
    ```
    
9. If successfully executed run the **lsusb** command once again to see if the device has been updated to
    
    ```
    Bus 002 Device 010: ID 19d2:0082 ONDA Communication S.p.A.
    ```
    
10. Once done click on **System->Preferences->Network Connections**
11. Click on the **Mobile Broadband** tab
12. Click on **Add**
13. Choose **South Africa**
14. Choose **Cell-C**
15. Leave the **Plan** to **Default**
16. Select **Connect Automatically** and **Available to all users** and leave the other information intact
17. Once **Saved** the **Cell-c Connection** will appear in the **Network Manager** and you will be able to connect to the **Internet**.
18. Enjoy
