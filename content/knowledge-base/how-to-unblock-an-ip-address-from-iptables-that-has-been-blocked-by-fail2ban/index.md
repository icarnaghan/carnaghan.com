---
author: "icarnaghan"
title: "How to unblock an IP address from IPTables that has been blocked by Fail2Ban"
date: 2018-04-07
---

1. Find the line number that needs to be removed from the IPTables
    
    ```
    sudo iptables -L fail2ban-SSH -v -n --line-numbers
    ```
    
    **Output**:
    
    ```
    Chain fail2ban-SSH (1 references)
    num   pkts bytes target     prot opt in     out     source               destination
    1        0     0 REJECT     all  --  *      *       84.93.156.103        0.0.0.0/0           reject-with icmp-port-unreachable
    2        0     0 REJECT     all  --  *      *       85.95.246.191        0.0.0.0/0           reject-with icmp-port-unreachable
    3        0     0 REJECT     all  --  *      *       82.207.98.112        0.0.0.0/0           reject-with icmp-port-unreachable
    4        0     0 REJECT     all  --  *      *       202.7.106.194        0.0.0.0/0           reject-with icmp-port-unreachable
    5        0     0 REJECT     all  --  *      *       90.156.212.140       0.0.0.0/0           reject-with icmp-port-unreachable
    6        0     0 REJECT     all  --  *      *       58.215.176.68        0.0.0.0/0           reject-with icmp-port-unreachable
    7        0     0 REJECT     all  --  *      *       212.55.218.134       0.0.0.0/0           reject-with icmp-port-unreachable
    8        0     0 REJECT     all  --  *      *       58.215.172.204       0.0.0.0/0           reject-with icmp-port-unreachable
    9        0     0 REJECT     all  --  *      *       200.106.147.29       0.0.0.0/0           reject-with icmp-port-unreachable
    10       0     0 REJECT     all  --  *      *       61.134.23.212        0.0.0.0/0           reject-with icmp-port-unreachable
    11       0     0 REJECT     all  --  *      *       71.179.168.28        0.0.0.0/0           reject-with icmp-port-unreachable
    12       0     0 REJECT     all  --  *      *       202.46.0.13          0.0.0.0/0           reject-with icmp-port-unreachable
    13       0     0 REJECT     all  --  *      *       173.224.112.170      0.0.0.0/0           reject-with icmp-port-unreachable
    14    1974  154K RETURN     all  --  *      *       0.0.0.0/0            0.0.0.0/0
    ```
    
2. Remove the line from the IPTables.
    
    **Command**
    
    ```
    iptables -D chain rulenum
    ```
    
    **Example**
    
    ```
    iptables -D fail2ban-SSH 6
    ```
    
    This will remove line 6
    
    ```
    6        0     0 REJECT     all  --  *      *       58.215.176.68        0.0.0.0/0           reject-with icmp-port-unreachable
    ```
    
3. Restart the IPTables
    
    ```
    service iptables restart
    ```
