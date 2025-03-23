---
author: "icarnaghan"
title: "ERROR: permission denied for sequence"
date: 2018-04-07
---

**Problem**: _PHP Warning:  pg\_query(): Query failed: ERROR:  permission denied for sequencename_ in PostgreSql

**Solution**:

To fix this problem, change the owner to the role that needs to access this sequence

```
ALTER TABLE sequencename OWNER TO rolename;
```

Change **sequencename** to your sequence name and **rolename** to the owner
