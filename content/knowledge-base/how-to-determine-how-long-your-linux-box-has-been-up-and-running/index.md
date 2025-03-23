---
author: "icarnaghan"
title: "How to determine how long your Linux box has been up and running"
date: 2018-04-07
---

- There are 2 commands that can be used namely the '**uptime**' and '**w**' commands
    -  **uptime** = _Shows how long Linux has been running, how many users are connected and then three system load averages._
    - _**w** = The w command gives a little bit more information.this could be useful if you have a busy system with lots of users connected._

- Open a new Terminal Session and type the **uptime** command. Your output will look similar to below

> 10:15:01 up  1:43,  4 users,  load average: 1.10, 1.18, 1.23

- Open a new Terminal Session and type the **w** command. Your output will look similar to below

> USER          TTY      FROM              LOGIN@   IDLE   JCPU   PCPU WHAT username   tty7     :0                        08:41         ?          5:46      0.28s  x-session username   pts/0    :0.0                   09:11         0.00s  0.10s     0.00s  w
