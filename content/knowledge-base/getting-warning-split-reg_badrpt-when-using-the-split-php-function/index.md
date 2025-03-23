---
author: "icarnaghan"
title: "Getting Warning: split(): REG_BADRPT when using the split PHP function"
date: 2018-03-22
---

Getting **Warning: split(): REG\_BADRPT** when using the split PHP function when I try to split a string after each question mark (?).

E.g.

```
$string = "ABC?DEF?BGT";
list($a,$b) = split('?',$string);
```

**Answer**:

- The reason why this is failing is split gives you the power to use regular expressions
- Use the **explode()** function instead
- If you really need to use the **split()** function try escaping the character eg. **'/\\?/'**
