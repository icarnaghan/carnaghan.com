---
author: "icarnaghan"
title: "SSL Labs Rating Woes"
date: 2018-03-08
categories: 
  - "coding"
  - "cybersecurity"
---

I was recently notified that one of the sites I support was getting a 'C' rating on SSL Labs. It turned out that there were three main issues that needed to be resolved. Two out of the three were relatively easy to find via the SSL Labs documentation, which required simple fixes to the ssl.conf file.

- **This server is vulnerable to the POODLE attack. If possible, disable SSL 3 to mitigate**. This was relatively easy to fix. I resolved it by modifying ssl\_protocols in the **ssl.conf** file - thank you Digital Ocean for your **comprehensive write-up** on this!
- **The server does not support Forward Secrecy with the reference browsers**. Again, more simple changes in the ssl.conf file. In case you run into a similar issue, be sure to read this helpful article, **Configuring Apache, Nginx, and OpenSSL for Forward Secrecy**.

The third issue, however, was not quite as straightforward: **This server accepts RC4 cipher, but only with older protocols**. I found a number of helpful articles on this stating that by adding !RC4 to exclude RC4 in SSLCipherSuite, will result in mitigation of this vulnerability. I spent quite a bit of time trying different cypher list combinations and always including !RC4, however no matter how many times I tweak this, restart httpd and revisit SSL Labs, I kept getting the annoying 'B' grade and RC4 complaint. For anyone facing similar issues, I highly recommend reading Hardening Your Web Server’s SSL Ciphers.

In the end, the problem I was facing was due to the fact I had a seperate vhosts file. I found the solution to my problem described in this very helpful entry on SuperUser, Disabling RC4 in the SSL cipher suite of an Apache server. The solution described here is to add the SSLCipherSuite specification in the Apache Directives textarea for each vhost. In my case, I had to add my SSLProtocol, SSLHonorCipherOrder, and SSLCypherSuite entries from ssl.conf into my vhosts file under my <virtualHost> tag. As the author of this post comments, it seems strange that it needs to be specified here also. Regardless if you are facing issues getting rid of RC4 and you are running vhosts, be sure to add your entries to your vhosts.conf file in addition to ssl.conf! Hopefully my wasted morning will benefit others.
