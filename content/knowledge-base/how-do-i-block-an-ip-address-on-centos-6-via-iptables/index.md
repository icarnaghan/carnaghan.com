---
author: "icarnaghan"
title: "How Do I Block an IP Address on Centos 6 via IPTables"
date: 2018-04-07
---

1. Open a new Terminal Window
2. Type the following command replacing **IPADDRESSTOBLOCK** with the IP Address that you wish to block.
    
    ```
    iptables -A INPUT -s IPADDRESSTOBLOCK -j DROP
    ```
    
    Explanation of above command:
    
    \-A = Append one or more rules to the end of the selected chain -s = Source, in this case the IP address to block -j = This indicates what to do if the rule matches
3. Save the Rule to the IPTables
    
    ```
    service iptables save
    ```
