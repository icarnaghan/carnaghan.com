---
author: "icarnaghan"
title: "Malicious Code Detection"
date: 2017-10-27
categories: 
  - "cybersecurity"
tags: 
  - "csec-650"
---

Malicious code detection is an ongoing obfuscation-deobfuscation game because of the nature of the malware or goals of the attacker. Detection of malicious executables known to an investigator is usually performed using signature-based techniques. In their forensic research article, Rozenberg, Guides, Elovici and Fledel (2010) made the point that obfuscated or encrypted files could not easily be detected this way. Instead they recommended a behavioral approach to real time detection. As hackers continue to find new and more advanced techniques to encrypt and hide malicious code, security personnel will have to continue to upgrade their skills and toolsets used in investigations, resulting in an ongoing obfuscation-deobfuscation game.

Malware is continually being enhanced in complexity and remains stealthy and elusive. It strives not only to hide its presence from detection, but also to detect and subvert existing anti-malware software. Jiang, Wang, and Xu (2007). Malware can hide itself in an asset using various techniques. Droppers and downloaders are simple programs that can bypass security checks, enter a network, and infect target systems. UMUC (n.d.). Droppers contain malicious code that is then executed on the infected system, whereas downloaders execute code and take advantage of the infected system’s internet connection to download malicious code. In combination with other types of malware including trojans, which are downloaded applications designed to appear harmless but contain malicious code, rootkits can be used to disguise the presence of code on an infected system by using techniques to manipulate the file system.

References:

Jiang, X., Wang, X., & Xu, D. (2007). Stealthy malware detection through vmm-based out-of-the-box semantic view reconstruction. In Proceedings of the 14th ACM conference on Computer and communications security (pp. 128-138). ACM.

Rozenberg B, Gudes E, Elovici Y, Fledel Y (2010) New Approach for Detecting Unknown Malicious Executables. J Forensic Res 1:112. doi:10.4172/2157-7145.1000112

UMUC (n.d.). Cybercrime Investigation and Digital Forensics. Retrieved from: https://learn.umuc.edu/content/enforced/248542-026828-01-2178-GO1-9046/CSES-650/CSES-650-week8/sco\_content/en/resources/csec650\_M08.pdf
