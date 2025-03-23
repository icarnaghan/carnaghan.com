---
author: "icarnaghan"
title: "How to get information on your CPU using Linux"
date: 2018-08-31
---

**NOTE**: This has been tested and tried on Ubuntu 9.04 and should work on other distributions.

In the command line interface (CLI) type in the command below and hit enter.

```
cat /proc/cpuinfo
```

This will display all information about your **CPU** similar as to example below

```
processor           : 0
vendor_id           : GenuineIntel
cpu family           : 6
model                  : 23
model name       : Intel(R) Core(TM)2 Duo CPU     P8400  @ 2.26GHz
stepping              : 6
cpu MHz              : 800.000
cache size           : 3072 KB
physical id           : 0
siblings                : 2
core id                  : 0
cpu cores             : 2
apicid                    : 0
initial apicid         : 0
fdiv_bug               : no
hlt_bug                 : no
f00f_bug               : no
coma_bug           : no
fpu                         : yes
fpu_exception     : yes
cpuid level           : 10
wp                          : yes
flags                      : fpu vme de pse tsc msr pae mce cx8 apic sep mtrr pge mca cmov pat pse36 clflush dts acpi mmx fxsr sse sse2 ss ht tm pbe nx lm constant_tsc arch_perfmon pebs bts pni dtes64 monitor ds_cpl vmx smx est tm2 ssse3 cx16 xtpr pdcm sse4_1 lahf_lm tpr_shadow vnmi flexpriority
bogomips              : 4521.73
clflush size            : 64
power management:
```

To only find the model name enter the following command:

```
grep 'model name' /proc/cpuinfo
```

```
The command above will have a similar output as below:

model name    : Intel(R) Core(TM)2 Duo CPU     P8400  @ 2.26GHz
```
