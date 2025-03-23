---
author: "icarnaghan"
title: "How to find the IP address of your Machine using Linux"
date: 2018-04-07
---

There are a number of ways to find the IP address. Examples below

1. ifconfig - _Deprecated, rather use the '"ip'" command
    
    _Input: {codecitation style="brush: shell;"}ifconfig{/codecitation}
    
    Output: {codecitation style="brush: shell;"} eth0      Link encap:Ethernet  HWaddr 00:0c:6e:c5:67:89 UP BROADCAST MULTICAST  MTU:1500  Metric:1 RX packets:0 errors:0 dropped:0 overruns:0 frame:0 TX packets:0 errors:0 dropped:0 overruns:0 carrier:0 collisions:0 txqueuelen:1000 RX bytes:0 (0.0 B)  TX bytes:0 (0.0 B) Interrupt:23 Base address:0x6c00{/codecitation}
2. Input: {codecitation style="brush: shell;"}ip addr show dev eth0{/codecitation}
    
    Output {codecitation style="brush: shell"} 2: eth0: <NO-CARRIER,BROADCAST,MULTICAST,UP> mtu 1500 qdisc pfifo\_fast state DOWN qlen 1000 link/ether 00:0c:6e:c5:67:89 brd ff:ff:ff:ff:ff:ff {/codecitation}
3. Input: {codecitation style="brush: shell;"}ping -I wlan0 www.google.com{/codecitation}
    
    Output: from 10.0.0.4 is the ip address{codecitation style="brush: shell;"} PING www.google.com (209.85.227.104) from 10.0.0.4 wlan0: 56(84) bytes of data. {/codecitation}
