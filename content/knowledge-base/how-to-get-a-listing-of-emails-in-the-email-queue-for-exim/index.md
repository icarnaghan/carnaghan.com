---
author: "icarnaghan"
title: "How to get a listing of emails in the email queue for Exim"
date: 2018-04-07
---

Enter the following command in the command line to print a listing of the message in the queue

```
exim -bp
```

The output in exact order will show

1. Time Queued, Size, Message-Id, Sender and Recipient
