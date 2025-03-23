---
author: "icarnaghan"
title: "Laptop Touchpad not working in Ubuntu"
date: 2018-04-07
---

**NOTE**: Tested in Ubuntu 10.04 and 10.10

Open a new **Terminal Window** and type in the following command and hit Enter

```
gconftool-2 --set --type boolean /desktop/gnome/peripherals/touchpad/touchpad_enabled true
```

This should solve the issue

For more information visit https://help.ubuntu.com/community/SynapticsTouchpad
