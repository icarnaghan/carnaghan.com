---
author: "icarnaghan"
title: "How to restart the service spamd in CPanel"
date: 2018-04-07
---

**Spamd** is a service for **Apache SpamAssassin** and to restart the **Spamd** service on a **CPanel** server you need to execute the following command from the **command line interface**

Restart **Spamd**

```
/scripts/restartsrv_spamd
```

To check the status of **Spamd** execute the following command

```
/scripts/restartsrv_spamd --status
```
