---
author: "icarnaghan"
title: "How to get information about your laptop battery using the Command Line within Linux"
date: 2018-04-07
---

Open a new command line window and type in the following command

```
cat /proc/acpi/battery/BAT0/info
```

 

This will display all information about your battery

```
present:                 yes
design capacity:         7200 mAh
last full capacity:      2732 mAh
battery technology:      rechargeable
design voltage:          11100 mV
design capacity warning: 135 mAh
design capacity low:     94 mAh
cycle count:          0
capacity granularity 1:  41 mAh
capacity granularity 2:  2597 mAh
model number:            GARDA43
serial number:           10102
battery type:            LION
OEM info:                SONYCorp
```
