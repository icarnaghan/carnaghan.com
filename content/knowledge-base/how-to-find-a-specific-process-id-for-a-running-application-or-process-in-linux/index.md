---
author: "icarnaghan"
title: "How to find a specific process id for a running Application or Process in Linux"
date: 2018-04-07
---

**NOTE**: Tested in **Ubuntu 9.04**

In this example we want to find the **process id** for Skype.

1. In the command line type in the command below {codecitation style="brush: bash;"}pgrep -l skype{/codecitation}
2. This will list the **process id** together with the process name for Skype. **\-l** = _List the name of the process_ {codecitation style="brush: bash;"}4322 skype{/codecitation}
3. To list only the **process id** type the command without the **\-l** option {codecitation style="brush: bash;"}pgrep skype{/codecitation}
4. This will only list the **process id** {codecitation style="brush: bash;"}4322{/codecitation}
