---
author: "icarnaghan"
title: "How to change the TIMEOUT of the GRUB loader Menu when your PC boots on Ubuntu"
date: 2018-04-07
---

**NOTE**: _Tested on Ubuntu 9.04_

1. Boot into Ubuntu
2. Open a new **Terminal Window**
3. Type in the following command: {codecitation style="brush: bash;"}sudo gedit /boot/grub/menu.lst{/codecitation}
4. Now **gedit** will open.
5. Located the following lines:
    
    ```
    ## timeout sec
    
    # Set a timeout, in SEC seconds, before automatically booting the default entry
    
    # (normally the first entry defined).
    
    timeout        10
    ```
    
6. Change **timeout        10** to the desired timeout seconds. eg. **timeout        4**
7. Save the file and exit.
8. Now the next time you Boot your PC the timeout change will take effect.
