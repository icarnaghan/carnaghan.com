---
author: "icarnaghan"
title: "How to get the last inserted id from a sequence in postgresql"
date: 2018-04-07
---

Use the **currval()** sequence function

```
SELECT currval('my_sequence');
```

Replace **_my\_sequence_** with your sequence, remember _**currval**_ returns the latest value that was obtained from your sequence in your session.
