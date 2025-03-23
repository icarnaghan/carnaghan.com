---
author: "icarnaghan"
title: "How to loop through the output of a Linux command in Bash"
date: 2018-04-07
---

```
for fileName in $(ls)
do
	echo $fileName
done
```

or a one liner

```
for fileName in $(ls); do echo $fileName; done
```

Replace the ls command with any Linux command
