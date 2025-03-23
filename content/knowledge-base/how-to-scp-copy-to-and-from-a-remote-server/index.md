---
author: "icarnaghan"
title: "How to SCP copy to and from a remote server"
date: 2019-01-18
---

To copy to a server (replacing 0.0.0.0 with the IP address)

```
scp -i ~/.ssh/your-private-key.pem /source/file/location user@0.0.0.0:/target/file/location
```

To copy from a server to your local machine within your current . directory

```
scp -i ~/.ssh/your-private-key.pem user@0.0.0.0:acf.sql .
```
