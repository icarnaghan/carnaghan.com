---
author: "icarnaghan"
title: "DNS Rebinding and Intrusion Detection with Contextual Signatures"
date: 2017-02-02
categories: 
  - "cybersecurity"
tags: 
  - "academic-papers"
  - "csec-640"
---

This article summarizes and analyzes discussion from two different articles on the subjects of DNS Rebinding and the use of contextual signatures with Intrusion Detection Systems.

DNS Rebinding is type of attack that was first documented in the mid 1990s. Since then it has become more prevalent through vulnerabilities inherent the way information is transmitted to and from a typical web browser using JavaScript. This topic is covered in depth along with the various methods of DNS rebinding, vulnerabilities and mitigations efforts.

Intrusion Detection Systems have a common problem with larger networks that drive a lot of traffic. The issue with false positives continues to be a challenge for network administrators and security personnel. This topic is discussed and a type of misuse detection via contextual signatures is analyzed.

## DNS REBINDING

### Protecting Browsers from DNS Rebinding Attacks

The following section provides a summary and analysis of the following 2009 publication:

Jackson, C., Barth, A., Boretz, A., Shao, W., & Boneh, D. (2009). Protecting Browsers from DNS Rebinding Attacks. ACM Transactions on the Web, Vol. 3, No. 1, Article 2, Publication date: January 2009.

DNS Rebinding is an old exploit that surfaced originally in the min ninety nineties in older network systems. It is as prevalent and important to understand today with the widespread of its use in recent years. The root cause of this vulnerability is to do with the inherent design of the Internet’s Domain Name System, whereby security policies are applied against a name instead of directly against an IP address. In their 2009 article, Jackson et al describe this as subverting the ‘same-origin’ principle by confusing the browser into mixing content controlled by distinct entities into a single security origin. An example of DNS Binding follows.

An internal corporate blog is behind a firewall so only company employees can access it.

1. A phishing email is sent from a malicious server residing on an IP address of 1.1.1.1.
2. The TTL of this server is set to 1 second instead of a typical limit of one hour or higher
3. An XMLHttpRequest (typically carried out on a standard JavaScript application) is made request to connect back in two seconds.
4. The original IP address of 1.1.1.1 has been disabled forcing the victim’s browser to rebind or request a new IP address from the server.
5. A new RFC1918 internal IP address is instead assigned of 10.0.2.1
6. The blog is accessed again with a new address header containing the malicious (typically throwaway) domain name, however it also contains an internal IP address.
7. The malicious host is bound and another XMLHttpRequest is made from the attacker who can now request potentially sensitive content in a request to the blog or application.

As seen in this example, the attacker not only can circumvent security processes in place as well as firewalls, but they can cyphen sensitive information inside the network. In addition to this, a spoofed IP address can cause other harm such as sending spam email from the network or worse, managing illegal botnets utilizing the network undetected. Jackson et al (2009) describe the process of pinning, whereby a browser would cache the IP address of a host for a set period of time regardless of TTL. Unfortunately, in modern browsers, vulnerabilities exposed by plugins and browser extensions can overcome this. DNS rebinding has essentially a low bar of entry which includes a modern day browser running JavaScript using the standard technologies that the Internet has been built on.

A user viewing a simple advertisement can be subject to this type of attack. The advertisement causes establishment of a connection and another request is then made in order to resolve the attacker’s domain name, in turn binding the host name to the IP address of the victim’s server. Jackson et al then go on to describe the various types of vulnerabilities exposed through DNS binding which are summarized below. The categorize these into standard and multipin vulnerabilities. Standard vulnerabilities are listed in the table below along with a brief summary for each.

| **Vulnerability** | **Summary** |
| --- | --- |
| **Multiple A Records**    | Multiple A Records are used in order to confuse the security policy of the Java Virtual Machine. While JVM is now protected, other variations of this has arisen in JavaScript. |
| **Time-Varying DNS**    | This is an extension of the original DNS rebinding attack that utilizes XMLHttpRequest causing a single A Record binding which in turn allows the attacker to exfiltrate data from the victim’s server. |
| **Pinning in Current Browsers**    | Pinning is the process in which the browser locks the resolved IP address for a period of time. Unfortunately workarounds exist in various browsers so this cannot be relied on as a sole security measure. |
| **Flash Player** | Earlier versions of Flash player exhibited vulnerabilities through the nature of the way this plugin permits socket connection to the target server because it does not pin host names to a single IP address. |

In addition to the standard vulnerabilities listed above, Multipin Rebinding Vulnerabilities, Jackson et al (2009) discussed multipin vulnerabilities, which occur when a number of plugins are installed on the user’s browser. Examples include Java LiveConnect and various applets that each can potentially pin host names to various IP addresses. They go on to discuss attacks using DNS rebinding including firewall circumvention and IP hijacking. Firewall circumvention can occur via the use of DNS rebinding. An attacker can connect to hosts behind a firewall that would not normally be possible or would be restricted. Once they have gained access they can steal data from hosts, compromise unpatched vulnerable hosts, and abuse internal open services. The term IP hijacking refers to the process of stealing other public IP address information from the victim revealing other potential targets within a network. According to Jackson et al, this can then lead to click fraud attempts, spam, framing of clients, and overcoming IP-based authentication.

Jackson et al demonstrate the effectiveness of a certain type of DNS rebinding attack that they carried out in the form of an experiment. The effort they put forward involved mounting DNS rebinding attacks in a controlled environment through the use of a flash-based advertisement. Their experiment was successful and yielded results showing successful attacks. The experiment also revealed how cost-effective it would be to exploit targets on a widespread scale.

Their paper concludes with several methods of defense against DNS rebinding attacks. They first discuss improvements that could be made to browser pinning to help defend against these types of attacks. They then provide some recommended defenses including securing socket access, firewall defenses involving proper configuration of internal IP addresses, effective blocking of traffic, and host-header checking. Out of all the defenses recommended, host header checking would probably be one of the best ways to counter DNS rebinding attacks, however it is very difficult to implement this across applications. It is also inconvenient for servers that do not know their host name.

Overall Jackson et all provided a good in depth view of the problem of DNS rebinding. Their initial analysis of the problem along with details of the different types of vulnerabilities helped frame the severity of this type of attack. There are other areas they could have gone into more depth with in the area of defenses. Better security policies could be put in place for ensuring that all hardware including network routers do not contain default passwords. In addition to this, all hosts, if provided with a SSL certificate could also mitigate these types of attacks. If the attack happened on a host with https, the user would at least receive an SSL DLS mismatch error, warning them of potential problems with their connection. If ignored however this would not mitigate the attack. Jackson, C., & Barth, A (2008). Johns, Lekiea & Stock (2013) propose a light weight extension to the Same-Origin Policy (SOP) which takes web server provided information into consideration.

Finally, other measures could take place within the enterprise that Jackson et all failed to mention including periodical scans of the network for exposure to malicious web browser that’s going through devices. Security policies could also be put in place to only purchase highly secure hardware that passes certain benchmarks. At the end of the day, DNS rebinding attacks are not going away as they only need a basic web browser running JavaScript in order to target their victim hosts.

## Network Intrusion Detection

### Enhancing Byte-Level Network Intrusion Detection Signatures with Context

The following section provides a summary and analysis of the following 2003 publication:

Sommer, R., & Paxson, V. (2003). Enhancing Byte-Level Network Intrusion Detection Signatures with Context. CCS’03, October 27–31, 2003, Washington, DC, USA.

Intrusion Detection Systems (IDS) come in various forms and provide different functionality. Host based systems are by their very name concerned with the host it is attached to. When the first intrusion-detection tools were designed, the target environment was a mainframe computer, and all users were local to the system considered. Debar, Dacier, & Wespi (1999). Host based IDS therefore evolved from this mentality to their current form which are typically software based and reside on a single host or computer. Network based IDS on the other hand are used to capture and analyze packets of data sent across an entire network. Another term called Intrusion Prevention Systems (IPS) is an IDS that also performs actions based on a set of criteria that alert the system based on suspicious traffic. The terms IDS and IPS are often interchangeable.

In their article, Sommer & Paxson discuss the various methods of detecting suspicious traffic within a network. They break this down into anomaly-based systems and misuse detection. Anomaly based systems typically baseline ‘regular’ or ‘normal’ traffic and anything that falls outside a specified threshold provides an alert. Essentially this happens when the IDS is looking for something out of the ordinary and different from common traffic in the network. There are several types of anomaly based detection and these include statistical anomaly and protocol anomaly. Statistical anomaly is the process of detecting what traffic actively differs from the baseline through the use of heuristics, i.e. what normally happens on the network. Protocol anomaly on the other hand looks at traffic that does not conform to the standard protocol specifications. An example of this might be traffic being sent via port 80 that is not HTTP. A downside of this type of detection is that normal changes in activity can sometimes cause false positives.

Misuse looks for particular, explicit indications of attacks. Sommer & Paxon (2003). The most common way misuse detection systems work is through the use of signature-based detection. Signature based can use string or pattern matching in order to determine if traffic is suspicious. This works in a similar manner to standard virus scanners and anti-malware tools. These patterns are stored in rules called signatures that can be built to look for specific attacks, e.g. SQL injection, cross-site scripting, etc. The downside to signature based detection is that it cannot detect zero-day attacks or new attacks that have not yet been cataloged in any signatures.

While Intrusion Detection Systems provide many ways to detect malicious traffic sent across a network, they also have some major drawbacks. One of the main weaknesses is apparent in larger networks with large amounts of traffic that can often yield false positives. In addition to this, any traffic that may be encrypted or using a legitimate form of encoding may be flagged mistakenly. Another concept called packet fragmentation enables network traffic to be broken down into smaller sizes and can therefore be used to avoid IDS detection. An example of a tool that does just that is fragroute enables evasion techniques that are quite simple. Li, Duan, & Jiang, J. (2013). An IDS can provide false positives, true positives, false negatives, and true negatives. Sommer & Paxon (2003) set out to reduce the number of false positives by proposing contextual signatures, allowing for better, more accurate reporting of malicious traffic alerts.

Their article maintained that false positives can potentially be greatly reduced if the match request has additional context at its disposal. This could involve fixing overly loose signatures that aren’t specific enough as well as providing additional information on activities or how the system responded to an attack, especially if the attack succeeded. They go on to discuss how implementation of such a system may happen via a building block approach integrating contextual information into new signatures as updating all legacy signatures would be unwieldly. In their article they used the freeware Network Intrusion Detection System (NIDS) Bro, which is “fundamentally neither an anomaly based system nor a signature-based system. It is instead partitioned into a protocol analysis component and a policy script component.” Sommer & Paxon (2003).

They discuss two levels of context including a low level with regular expressions for matching focusing on connection state, as well as a high level focusing on the state of the network and taking advantage of the semantic information made available by Bro’s protocol analysis and scripting language. Their research involved using the NIDS SNORT signatures with Bro enabling them to leverage Bro’s context and state-management mechanisms to improve the overall quality of alerts. They evaluated their signature engine against Snort as a reference comparing both systems. Several problems were documented including differing internal semantics, incompatible tuning options, difficulty of devising representative input, and sensitivity to hardware particulars. They found the comparisons less effective, however overall the research suggested that Bro maintained better performance as was the case in mitigation of false positives. Overall their article provided an in-depth review of the various types of IDS, the challenges they pose, and the overall experiments with contextual signatures. It wasn’t however clear as to the amount of work needed to implement these contextual scripts vs the final overall improvement of performance.

## References

Debar, H., Dacier, M., & Wespi, A. (1999). Towards a taxonomy of intrustion-detection systems. Computer Networks 31 (1999) 805-822. Retrieved from: http://galaxy.cs.lamar.edu/~bsun/seminar/example\_papers/IDS\_taxonomy.pdf

Li, D., Duan, H., & Jiang, J. (2013). New Intrusion Detection Evasion Techniques with Signature Based Segmentation and Customized Overlap Patterns. In Proceedings of the 2013 International Conference on Business Computing and Global Informatization (BCGIN '13). IEEE Computer Society, Washington, DC, USA, 946-949. DOI=http://dx.doi.org/10.1109/BCGIN.2013.253

Jackson, C., & Barth, A (2008). Beware of Finer-Grained Origins. Retrieved from: http://seclab.stanford.edu/websec/origins/fgo.pdf

Jackson, C., Barth, A., Boretz, A., Shao, W., & Boneh, D. (2009). Protecting Browsers from DNS Rebinding Attacks. ACM Transactions on the Web, Vol. 3, No. 1, Article 2, Publication date: January 2009.

Johns, M., Lekies, S., & Stock, B. (2013). Eridicating DNS Rebinding with the Extended Same-Origin Policy. Proceedings of the 22nd USENIX Security Symposium. Retrieved from https://www.usenix.org/system/files/conference/usenixsecurity13/sec13-paper\_johns.pdf

Sommer, R., & Paxson, V. (2003). Enhancing Byte-Level Network Intrusion Detection Signatures with Context. CCS’03, October 27–31, 2003, Washington, DC, USA.
