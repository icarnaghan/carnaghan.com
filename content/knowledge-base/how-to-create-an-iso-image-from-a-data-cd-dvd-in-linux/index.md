---
author: "icarnaghan"
title: "How to create an ISO image from a data CD/DVD in Linux"
date: 2018-04-07
---

- Open a new **Terminal Window**
- Type in the following command
    
    ```
    dd if=/dev/sr0 of=myISO.iso
    ```
    
    **Explanation dd =** _covert and copy a file_ **if =** _read from FILE instrad of stdin_ **/dev/sr0 =** _This is your cd-rom device,_ _please remember to replace this with your device_ **of =** _write to FILE instead of stdout_ **myISO.iso =** _The location and filename where you want the ISO file saved_
