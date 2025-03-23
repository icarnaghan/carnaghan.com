---
author: "icarnaghan"
title: "How to check if a Bash variable is empty"
date: 2018-04-07
---

```
if [ -z "$VARIABLE" ]
```

If **$VARIABLE** is _not set_ or _empty_ the _if_ statement above will _return true_, the **\-z** option tests for a _zero-length string,_ so whether **$VARIABLE** is _not set_ or _empty_ the _if_statement will _return true_
