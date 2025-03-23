---
author: "icarnaghan"
title: "How to loop through lines in a file using Bash"
date: 2018-04-07
---

```
for i in $(cat myFile.txt); do echo $i; done
```

The above code executes a **for loop** and then **echo's** out each line in the file **myFile.txt**
