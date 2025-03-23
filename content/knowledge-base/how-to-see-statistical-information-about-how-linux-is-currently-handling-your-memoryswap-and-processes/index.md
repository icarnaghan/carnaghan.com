---
author: "icarnaghan"
title: "How to see statistical information about how Linux is currently handling your memory,swap and processes"
date: 2018-04-07
---

1. Open a new **Terminal Window** if not already in **command line**.
2. Type in the '**top**' command.
3. Now a list of processes will appear as below.
    
    top - 09:38:39 up  1:09,  2 users,  load average: 0.43, 0.29, 0.29 Tasks: 165 total,   2 running, 163 sleeping,   0 stopped,   0 zombie Cpu(s):  4.5%us,  3.2%sy,  0.0%ni, 92.2%id,  0.0%wa,  0.2%hi,  0.0%si,  0.0%st Mem:   1974152k total,  1622216k used,   351936k free,    68908k buffers Swap:  2493588k total,        0k used,  2493588k free,  1040980k cached
    
    PID    USER      PR  NI  VIRT   RES  SHR S   %CPU %MEM    TIME+  COMMAND 3652 root           20   0   412m  96m  51m S    9            5.0           9:05.48 Xorg 
4. There are a number of interactive controls with can be used together with the '**top**' command, including Killing processes and changing the priorities of processes.
    - For example killing processes use the **K key** and then type in the **process id**which you wish to kill.
5. Type in the following command to find out more about the **top** command: **man top**
