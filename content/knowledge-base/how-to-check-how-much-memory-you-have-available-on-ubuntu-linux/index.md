---
author: "icarnaghan"
title: "How to check how much memory you have available on Ubuntu (Linux)"
date: 2018-04-07
---

1. Open a **Terminal Window** if not yet in **command line**
2. Type in the following **command**: cat /proc/meminfo
3. This will display a **resultset** as below of how much **memory** you have left

> _MemTotal:        1974152 kB MemFree:          373196 kB Buffers:          107380 kB Cached:           881568 kB SwapCached:        13288 kB Active:           872248 kB Inactive:         640876 kB Active(anon):     599548 kB Inactive(anon):    25012 kB Active(file):     272700 kB Inactive(file):   615864 kB Unevictable:           8 kB Mlocked:               8 kB HighTotal:       1103016 kB HighFree:           1612 kB LowTotal:         871136 kB LowFree:          371584 kB SwapTotal:       2493588 kB SwapFree:        2461148 kB Dirty:                72 kB Writeback:             0 kB AnonPages:        514288 kB Mapped:           122972 kB Slab:              50072 kB SReclaimable:      32964 kB SUnreclaim:        17108 kB PageTables:         5136 kB NFS\_Unstable:          0 kB Bounce:                0 kB WritebackTmp:          0 kB CommitLimit:     3480664 kB Committed\_AS:    2313760 kB VmallocTotal:     122880 kB VmallocUsed:       23780 kB VmallocChunk:      93580 kB HugePages\_Total:       0 HugePages\_Free:        0 HugePages\_Rsvd:        0 HugePages\_Surp:        0 Hugepagesize:       4096 kB DirectMap4k:       16376 kB DirectMap4M:      888832 kB_
