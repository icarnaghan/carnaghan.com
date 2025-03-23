---
author: "icarnaghan"
title: "What are Covert Channels?"
date: 2016-11-05
categories: 
  - "cybersecurity"
tags: 
  - "csec-640"
---

A covert storage channel occurs when illegitimate hidden information or data is sent secretly via a legitimate communication channel. The process occurs through the manipulation of communications medium in an unconventional way in order to transmit data that is unseen in everyday operations. Thyer (2008). An example of a covert storage channel involves the hiding of data in ICMP error echoing functionality. OWASP (n.d.). Due to the specification, data can be sent to cause a host to leek information or provide verbose error messages potentially revealing sensitive operating system information. This type of covert channel could lead to gaining knowledge of vulnerabilities and possible future attacks. It can be mitigated by clearing out all reserved fields prior to transmission to ensure no sensitive data is leaked.

Timing channels on the other hand gain information through a repeated behavior over a period of time. This type of information can yield important information on system conduct with regards to processing, authentication and other areas that could reveal vulnerabilities. An example of a covert timing channel could involve testing to see how long a system responds to illegal credentials for authentication. This would need to be mitigated by securing authentication systems to either restrict repeated traffic from a given source or update password policies to vary time based on incorrect login attempts.

References:

- Cabuk, S., Brodley, C. E., & Shields, C. (2004, October). IP covert timing channels: design and detection. In Proceedings of the 11th ACM conference on Computer and communications security (pp. 178-187). ACM.
- OWASP (n.d.). Covert storage channel. Retrieved from https://www.owasp.org/index.php?title=Covert\_storage\_channel&setlang=en.
- Thyer, J. (2008). Covert Data Storage Channel Using IP Packet Headers. Retrieved from: https://www.sans.org/reading-room/whitepapers/covert/covert-data-storage-channel-ip-packet-headers-2093
