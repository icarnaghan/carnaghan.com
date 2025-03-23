---
author: "icarnaghan"
title: "How to set the default Java version on Linux"
date: 2018-04-07
---

1. Open a new **Terminal Window**
2. Execute the following command:
    
    ```
    sudo update-alternatives --config java
    ```
    
3. Output similar to the below will show:
    
    ```
    There are 4 choices for the alternative java (providing /usr/bin/java).
    
      Selection    Path                                            Priority   Status
    ------------------------------------------------------------
      0            /usr/lib/jvm/java-8-oracle/jre/bin/java          1092      auto mode
    * 1            /usr/lib/jvm/java-7-openjdk-amd64/jre/bin/java   1071      manual mode
      2            /usr/lib/jvm/java-8-openjdk-amd64/jre/bin/java   1081      manual mode
      3            /usr/lib/jvm/java-8-oracle/jre/bin/java          1092      manual mode
      4            /usr/lib/jvm/java-9-openjdk-amd64/bin/java       1091      manual mode
    
    Press <enter> to keep the current choice[*], or type selection number:
    ```
    
4. Enter the number next to your preferred version and hit the **Enter key**
5. Now the **default Java version** will be changed.
