---
author: "icarnaghan"
title: "How to get the date for next week friday or any other day of the week via the command line in Linux"
date: 2018-04-07
---

1. Open a new **Terminal Window**
2. Type in the following command
    
    ```
    date -d fri
    ```
    
    **Description**:
    - **date** = print or set the system date and time
    - **\-d** \= display time described by STRING, not \`now'
    - Replace **fri** with any day of the week you prefer.
3. This will output something similar as below
    
    ```
    Fri Aug  6 00:00:00 SAST 2010
    ```
