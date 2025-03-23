---
author: "icarnaghan"
title: "Mitigating DoS or Distributed DoS (DDoS) attacks"
date: 2017-01-16
categories: 
  - "cybersecurity"
tags: 
  - "academic-papers"
  - "csec-640"
---

Denial of Service (Dos) and Distributed Denial of Service (DDoS) attacks have continued to prove to be one of the most challenging threats in modern times. While DoS has been around for some time, the methods used and practices of distributed botnets and automated scripts have continued to grow in sophistication. This paper survey’s three peer reviewed papers in the areas of Denial of Service Detection, Prevention and Mitigation. Each of these sections provide a rationale for the publication selected along with an overview of the proposed techniques and / or application solutions. Each section concludes by highlighting some benefits and drawbacks for each proposed technique. Additional supporting research has been carried out contribute to this overall paper as outlined in the references section at the end.

This paper concludes with some final thoughts on Denial of Service and Distributed Denial of Service, which is an ever changing field of research in its own right. The topics and articles presented throughout this paper reflect recent publications due to the ever changing nature of the processes and techniques used to combat these types of attacks.

## Denial of Service Attacks Explained

As the Internet has evolved and grown exponentially over the last decade, more people have come to rely on the accessibility of feature rich web applications to do their day to day business. Large e-commerce platforms have become the norm and many individuals rely heavily on banking web applications to manage their finances in a day to day bases. Unfortunately, with all of the modern conveniences has come risk and threat of security implications. Every other day news organizations release articles detailing the latest breaches from large and small organizations a like. One of the most persistent and ongoing threats in modern times has been the Denial of Service (Dos) and Distributed Denial of Service attacks, which have brought down entire organization infrastructures.

Denial of Service attacks, sometimes referred to as SYN Flood attacks, are caused through exploitation of the TCP protocol. The attacker sends a large number of TCP/SYN packets using a forged address. Because of this, the destination server is unable to successfully establish a proper connection due to the source being unreachable. Each time the server attempts to establish a connection, resources are used up with the flooding of packets causing eventual slow down or non-responsiveness. In contrast to this, a Distributed Denial of Service where hundreds or even thousands of compromised hosts combine an attack against a single target. The goal of a DDoS attack is similar to that of a DoS attack where by the perpetrator wishes to cause harm to the primary target’s system, i.e. to disable legitimate traffic access. This is achieved by unknowing ‘infected’ systems referred to as secondary targets. Quite often such systems have become compromised with malicious software and unwittingly become part of a larger botnet. Therefore, a DDoS attack by definition is an attack intended to cause a service to become unavailable or unusable. Desai et al (2016).

There are several symptoms of a Denial of Service attack. First and foremost, the targeted system will experience a massive increase or spike in traffic, resulting in a slowdown of the network. In addition to this, the victim may experience non-responsiveness or accessibility of a particular website or web application resource. Another side effect may be an immediate surge of spam received in email accounts belonging to the network. McDowell (2009). Distributed Denial of Service attacks can be broadly segregated into three main types:

Volume Based Attacks: These types of attacks include UDP floods, whereby a perpetrator may overwhelm random ports on a targeted host with IP packets containing UDP datagrams.

Protocol Attacks: These include the aforementioned SYN attacks, which involve fragmented packet attacks, which consume server resources. The end goal is to flood the target to the point where resources will not be responsive to legitimate users.

Application Layer Attacks: These attacks include low-and-slow attacks targeting specific web application vulnerabilities. They can include get/post floods via the HTTP protocol and can often target different operating systems including Windows, Linux and varying web application servers with an end goal of crashing the server.

The sections that follow detail a literature review of various different peer reviewed papers that tackle the issues behind detection, mitigation, and prevention of Denial of Service attacks. As this is an ongoing problem and has evolved in recent years to much larger attacks, the papers chosen for these sections are no older than two years.

## Signal and Image Processing Based Detection

When reviewing current literature for Denial of Service attack detection a peer reviewed IEEE publication by Pukkawanna, Hazeyama, Kadobayashi & Yamaguchi (2014) was identified as an interesting take on detection of Denial of Service attacks. This paper entitled Investigating the utility of S-transform for detecting Denial-of-Service and probe attacks, presented a novel approach at detecting attacks through the use of S Transform and image processing. This paper is both relevant to the field as well as recent and their proposed method of detection holds merit.

S Transform is a time frequency distribution, which Pukkawanna et al (2014) describe as an extension of Wavelet Transform, to reveal abnormal frequency components caused by attacks in a traffic signal, for example, a time series of a number of packets transferred over a network. In their paper, Pukkawanna et al describe the current limitations of existing Intrusion Detection Systems (IDS) and Intrusion Prevention Systems (IPS). Traditional IDS systems use pre-defined attack signatures or patterns, which allow the systems to determine new threats. Unfortunately, this also means that such systems must be updated continually with new attack patterns as they are made available by vendors. The S Transform method described in this paper mitigates the need for such updates.

Pukkawanna et all describe how their proposed technique would work using S Transform and image processing. S Transform provides a method for analyzing time series data of the current traffic coming in and out of the network. Their research is partially based on existing picture processing research from the 1970s by Nobuyuki Otsu, who authored the paper ‘A Threshold Selection Method from Gray-Level Histograms’. Their technique describes three main steps of their detection process:

1. Calculate the time-series of the number of packets per second from raw traffic data (e.g., traffic collected from a router).
2. An image is produced from the S Transform data in step 1 showing the frequencies of traffic. The background of the image contains typical traffic, whereby the foreground objects illustrate abnormal patterns.
3. Foreground objects (or those identified as abnormal traffic) are detected by Otsu’s image segmentation technique.

One of the biggest advantages of using S Transform with image processing in this way is the mitigation of the need for prior data as other traditional systems needs for identifying abnormal patterns. This coupled with the fact it is built on existing research is a huge benefit. In their experiments Pukkawanna et al observed that with the exception of a low-rate attack, their technique was successful at detecting abnormal traffic behavior resulting in positive detection of Denial of Service attacks. Since however this technique is still in its infancy, it is not known how well such a system would hold up to larger Distributed Denial of Service attacks without more research. It will be interesting to see how this method impacts detection techniques in years to come.

## Filter Based Application Prevention

Earlier this year, Desai, Patel, Somaiya, & Vishwanathan (2016) published an interesting article in the International Research Journal of Engineering and Technology (IRJET). Their paper title was ‘Prevention of Distributed Denial of Service Attack using Web Referrals’. This paper was chosen for review due to its authenticity of being published in a peer reviewed journal. Furthermore, since this was a more recent take on Denial of Service prevention from earlier this year, it was more relevant to the discussion here looking at current methods and theories.

In their paper, Desai et al (2016) discuss the feasibility of implementing a web referrals Java-based filter application with the goal of restricting the number of requests in a particular time. Other research has been done on web referral based architectures in recent years including Dewiyana et al (2013) paper, which discusses Web Referral Architecture for Privileged Service (WRAPS). In their paper, they focus on trusted web application services. Desai et al (2016) proposed a filtering system to manage IP access permissions and provide alerts whenever suspicious activity occurred including but not limited to heavy load on the server, file extension examination reviewing suspicious types of files, for example with a .exe extension, and overall size limit monitoring among other traits. Their final proposed system includes five modules, which have been summarized in table below. Their paper outlined current problems with Denial of Service attacks and set out to detail some of the design specifications of their proposed solution.

Desai et al (2016) go on to distinguish between the terms byte pattern, flow pattern, and traffic pattern. They describe byte patterns as a series of bytes within a packet that gets sent to the server. Flow patterns are a serial of packets that are used together to form a specific attack. A traffic pattern is an aggregation of multiple flow patterns that target the same site or application. Their proposed filtering system has been designed in order to accommodate all of these types of attacks while keeping track of user activities. By carefully monitoring and analyzing user behavior, the proposed system has been designed to prevent flooding, phishing , buffer overflow, and SYN flood attacks. They assert that the system can be used to protect large and small systems alike. The table that follows highlights the filters used in this system. The nature of this system has been designed to allow for different types of attacks and circumstances that may lead to Denial of Service vulnerabilities.

| **Filter Name** | **Description** |
| --- | --- |
| Credential Filter | As its name suggests, this filter is responsible for confirming valid credentials provided by users of the system. |
| Rate Attempt Filter | Similar to a locking mechanism, this filter monitors for failed credential attempts and prevents access after a threshold limit has been met. |
| Size Limit Filter | This filter monitors file size and overall bandwidth to ensure resources are not eaten up quickly. Limits are therefore placed on everyone including legitimate users of the system. |
| Load Limit Filter | This filter is designed to limit the number of users allowed to access any given resource at any given time. |
| IP Filter | The IP filter keeps a close eye on the various IP addresses used to access the system. It maintains a ‘black list’ of IP addresses which should not have access and monitors for suspicious activities. |

One of the biggest strengths of the approach outlined here is scalability. Desai et al (2016) concluded to assert their proposed system would be easy to implement in order to prevent Distributed Denial of Service attacks via the assistance of the above mentioned filters both in small and large scale systems. Their proposed design works on the application layer of the client as well as the admin side web application and has been architected in Java. While the web services provided by the application work to ensure no authorized users are ever denied access to the system, there are potentially scenarios whereby legitimate users may temporarily lose access due to error on their part or misconfiguration. Overall however this seems to be a very feasible solution for Denial of Service prevention.

## Mitigation using Stratified Architecture

Earlier this year Prakash, Satish, Bhargav, and Bhalaji authored the ScienceDirect peer reviewed publication ‘Detection and Mitigation of Denial of Service Attacks using Stratified Architecture.’ In their paper they proposed a layered based approach to mitigating Denial of Service attacks. Like other papers reviewed thus far, this publication is one of the more recent pieces of work in this field of research. The publication was peer reviewed and also presented at the 4th International Conference on Recent Trends in Computer Science and Engineering.

In their paper, Prakash et al (2016) provide a brief overview of the existing types of Denial of Service (Dos) attacks grouped by network level, application level, operating system level, and data level. They propose a layered approach to mitigation and their publication breaks down by literature review and experimentation of their approach. Their final proposed technique is a combination of three layers outlined in the table below.

| **Layer** | **Description** |
| --- | --- |
| Puzzle | The purpose of a puzzle solving layer is to present an obstacle that only a human user would be able to solve. This mitigates threat from botnets or other automated attack processes. Prakash et al (2016) propose three different types of puzzle algorithms:  1.     Dot and Shape  2.     Integer Arithmetic  3.     Entering a string |
| Mac Filtration | Similar to blacklisting IP address tables, Mac Filtration is process of maintaining two tables of Mac addresses; a ‘legal’ table and an ‘intruder’ table. The process follows:  1.     Check if address is in intruders table – if so deny  2.     Check if address is in legal table – if not, permit up to specified limit, if limit broken push into intruders table,  3.     Tables are flushed periodically (typically within minutes) |
| Cryptography Based Authentication | An RSA algorithm is used and each user has two public and private key pairs for accessing the system. |

In their experiments, Prakash et al (2016) were able to successfully mitigate Denial of Service attacks. The notion of a multi-layer approach seems to be valid here and provides additional security. One of the drawbacks of such a system would be the complexity forced upon the user, especially for those unfamiliar with using public and private key sets. As with other techniques, using a puzzle algorithm may also cause additional user anxiety or frustration. As a whole though, this approach seems to work well based on the findings recorded in this paper. As with other more modern approaches, it will be interesting to see how if this will develop over time or accrue mass adoption.

## Further Discussion and Conclusion

Denial of Service and Distributed Denial of Service attacks have grown in popularity in recent years. While these are one of the oldest security threats, they are also constantly evolving and evoking more damage on larger systems as Internet Applications grown both in complexity and popularity. The three papers outlined in this review provided some of the more modern insight into detection, prevention and mitigation techniques. From the preliminary research however, it was clear that there is much literature in this field and it continues to evolve and change along with the complexity of such attacks.

In order to remain secure, it will be important for organizations and researchers to continue experimentation with new processes and methods for defense, mitigation and detection. It is not enough to rely on techniques that may have worked ten or maybe even just five years ago. Because of the ever changing nature of these types of threats, this will no doubt be a field of research and expertise that will continue to grow and change into the upcoming years ahead.

## References

Carl, G., Rai, S., Kesidis, G., & Brooks, R. (2006). Denial-of-Service Attack-Detection Techniques, IEEE Internet Computing, vol. 10, no. , pp. 82-89, January/February 2006, doi:10.1109/MIC.2006.5

Dewiyana, A., Hadi, A, Hj, F., Fakariah, A., Mohd, H. A. (2013) IDS Using Mitigation Rules Approach to Mitigate ICMP Attacks, Advanced Computer Science Applications and Technologies (ACSAT) 2013 International Conference on, pp. 54-59, 2013.

Desai, M., Patel, S., Somaiya, P., Vishwanathan, V. (2016). Prevention of Distributed Denial of Service Attack using Web Referrals. International Research Journal of Engineering and Technology (IRJET). Volume: 03 Issue: 04 | Apr-2016.

Devare, A., Shelake, M., Vahadne, V., Kamble, P., & Tamboli, B. (2016). A System for Denial-of-Service Attack Detection Based on Multivariate Correlation Analysis. International Research Journal of Engineering and Technology (IRJET). Volume: 03 Issue: 04 | Apr-2016

Francois, J., Aib, I., Boutaba, R. (2012). FireCol: A Collaborative Protection Network for the Detection of Flooding DDoS Attacks. IEEE/ACM Transactions on Networking \[1063-6692\] François yr:2012 vol:20 iss:6 pg:1828 -1841

McDowell, M. (2009). Understanding Denial-of-Service Attacks. Security Tip ST04-015. Retrieved from https://www.us-cert.gov/ncas/tips/ST04-015

Otsu, N. (1979). A Threshold Selection Method from Gray-Level Histograms. IEEE Transactions on systems, man, and cybernetics, VOL. SMC-9, No. 1, January 1979

Prakash, A., Satish, M., Sri, T., Bhargav, S., & Bhalaji, N. (2016). Detection and Mitigation of Denial of Service Attacks Using Stratified Architecture. Procedia Computer Science Volume 87, 2016, Pages 275–280

Pukkawanna, S., Hazeyama, H., Kadobayashi, Y., & Yamaguchi, S. (2014). Investigating the utility of S-transform for detecting Denial-of-Service and probe attacks, The International Conference on Information Networking 2014 (ICOIN2014), Phuket, 2014, pp. 282-287. doi: 10.1109/ICOIN.2014.6799482

Yu, S., Zhou, W., & Doss, R (2008), Information theory based detection against network behavior mimicking DDoS attacks, IEEE communications letters, vol. 12, no. 4, pp. 319-321.

Wang, X., & Reiter, M., K. (2010). Using Web-Referral Architectures to Mitigate Denial-of-Service Threats," in IEEE Transactions on Dependable and Secure Computing, vol. 7, no. 2, pp. 203-216, April-June 2010. doi: 10.1109/TDSC.2008.56
