---
author: "icarnaghan"
title: "How to convert RPM packages to DEB packages using Ubuntu"
date: 2018-04-07
---

**NOTE**: Has been tested on Ubuntu 9.10

1. In **Ubuntu** open **Synaptic Package Manager** '_System->Administration->Synaptic Package Manager_'
    
    ![Synaptic Package Manager](images/a1.png "Synaptic Package Manager")
2. Now we need to install 2 apps called **alien** and **fakeroot**
    
    - **alien** - Convert and install rpm and other packages
    - **fakeroot** - Gives a fake root environment
    
    ![Quick Search](images/a2.png "Quick Search")
3. To install them simply type _**alien**_ in the **Quick search** box and mark for installation and do the same for _**fakeroot**_.
4. Once both have been marked for installation click on **Apply
    
    **![Apply](images/a3.png "Apply")
5. Now these packages will be installed, after installation they will be ready to use.
6. Open a new **Terminal Session** and execute the command below with your **RPM package** {codecitation class="brush: bash;"}fakeroot alien RPM\_PACKAGE.rpm{/codecitation}
    
    This will create a **DEB** package in the same directory as your **RPM** package, for more info about alien use the _**man alien**_ command
