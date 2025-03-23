---
author: "icarnaghan"
title: "An analysis of different data sources used in a forensics investigation"
date: 2017-11-25
categories: 
  - "cybersecurity"
tags: 
  - "academic-papers"
  - "csec-650"
---

This article provides an overview of four different data sources used in various forensics investigations. The first source includes system log files containing system logs within the operating system as well as an overview of some tools that can be used in order to effectively understand these logs. File systems are also discussed including the effectiveness of metadata and their overall relevance to an investigation or analysis. The third source involves intrusion detection and prevention systems that give a greater overview of traffic at the network layer. Finally, the most volatile of data sources, memory is examined in depth along with the impact such data may have on an investigation.

Each of these data sources provide a different impact on forensics investigations depending on the incident being analyzed. A thorough overview of each of these data sources is provided along with a matrix on the impact they would have on one of three different types of investigation involving network intrusion, malware detection, and insider file deletion. The context and details of each incident are not discussed and remain unknown, therefore assumptions have been made in order to broadly prioritize each in according the priority and overall impact.

## Introduction

Forensic analysis requires the acquisition and management of many different types of evidence, including individual disk drives, RAID sets, network packets, memory images, and extracted files. Cohen & Schatz (2009). In recent years understanding these sources along with their relevance in different types of investigations has become paramount in the field of digital forensics. This paper explores data sources used to uncover evidence in the situations of network intrusion, malware installation and insider file deletion. These three distinct but often as equally damaging scenarios require a different approach within the forensics process with different data sources supporting the analysis.

First and foremost, network intrusions are becoming commonplace in the news, which affect everyone from large corporations to individual victims of such cybercrime activities as identity theft. According to Mukherjee and Levitt (1994), a secure network should provide data confidentiality, data and communications integrity, and assurance against denial of service. In the last couple of months alone, most of the country has learned about the Equifax breach, which was the latest in a long line of network intrusions we’ve heard about over the last year impacting millions of individuals. This particular breach affected their unpatched systems affected by Apache’s open-source Struts software, a vulnerability that should have been mitigated months before the breach took place. Brandom (2017).

Often times equally as damaging, is the spread of malicious software or code (malware) that can potentially infect systems that result in massive financial damages to those targeted. Bergeron et al (2001) describe malicious code as “pieces of code that can affect the secrecy, the integrity, the data and control flow, and the functionality of a system.”   The two most common cyber-attacks come in the form of cross-site scripting and SQL server injections, which take advantage of vulnerabilities in the systems they target.  Often these vulnerabilities are present because of poorly written code where little or no thought has been given to systems security.  Vulnerabilities can also be caused by poorly configured servers or network firewalls.

Conrad et al (2009) states that within an organization, the employee population is the source of potential malicious insiders. Insider file deletion or tampering of information assets has become a major problem for organizations in recent years as employees and consultants have greater access to systems that contain confidential data. Organizations continue to combat this threat by utilizing comprehensive roles based access systems and restricting access appropriately. The principle of least privilege requires users and applications within the operating system to be given the most restrictive access possible to perform their tasks. (Motiee, Hawkey, & Beznosov 2010).

The sections that follow cover four main data sources are used in digital forensics. These sources include system logs, file systems, intrusion detection and prevention systems, and computer memory images. Within each of these sections, the sources themselves are ranked according to their overall usefulness in regard to the three different types of cybersecurity incidents mentioned above.

## Logs

Tanenbaum (2009), describes the operating system conceptually in two basic modes; Kernel mode and User mode. The kernel can be considered the ‘core component’ of the operating system. Goodrich and Tamassia (2011). It is the kernel that manages all of the low-level details around memory management, looking after all running system processes, and working directly with system hardware. In contrast to this, the user mode is that part of the operating system that contains user interface programs and the applications that the user interacts with. In digital forensics operations, both of these sides of the operating system are important. This section examines in greater depth, the user mode, more particularly, logs that are yielded from activities that take place here and can contribute to a forensics analysis. Later, we will explore the kernel mode, more specifically, taking a snapshot of memory as another data source to consider in forensics analysis.

Most modern operating systems contain in-depth logs that can provide useful information on the day to day running of applications and services sitting in what Tanenbaum considers the user mode. Most modern web servers contain many different types of logs that can be used across different services. Tools such as New Relic and Splunk are often used to aggregate system logs providing an easier to understand reporting tool for the maintainers of such infrastructure. Logs that can be useful in an investigation can be seen in three different categories:

### System Logs

Syslog and RSyslog, are log files that contain entries (or messages) from different application services such as an apache web server. They also provide hooks into web applications and other services that can provide additional insight into for example an enterprise Content Management System, or an online inventory management system. SysLog is typically used in Linux or Unix based environments. It captures events not only from the operating system and hosted applications, but also other servers connected to the infrastructure such as database systems. It is typically used by systems administrators and software developers to keep an eye on the overall health of systems. In addition to monitoring for general messages, errors, and events triggered by applications, it also provides a good data source for forensics examination.

### Impact and Usefulness in Forensics Investigations

Log files in general provide the equivalent of an electronic fingerprint with an added element: we know at what time that fingerprint was generated, so we are able to reconstruct what happened and in what order. Sadowski (2010). In order for log files to be meaningful, they need setup correctly to capture relevant event based information. This information in turn needs to be persisted to a reliable data storage system that cannot be compromised easily. Sadowski (2010) list eight different ways information can be persisted to logs based on frequency and verbose level. Depending on how these are set can be the difference in useful information in a forensics case to non-useful.

As mentioned earlier, tools like Splunk and New Relic can also be used in conjunction with system logs and can provide greater insight into any security incidents that may have taken place on the server. Splunk also has third party tools available to it such as Forensic Investigator, which is designed to be a Splunk toolkit for the first responder. It includes virus, metascan lookups along with a range of other tools to assist the forensics investigator. In addition to system logs, other logs also can provide information needed in an investigation such as server access logs and user management logs. We will touch on access later under Intrusion Detection and Prevention Systems.

**Table 1: Logs Matrix**

|   | **Highest Impact** | **High Impact** | **Medium Impact** |
| --- | --- | --- | --- |
| **Network Intrusion** |  | \* |  |
| **Malware Detection** |  |  | \* |
| **Insider file deletion** | \* |  |  |

Table 1 summarizes the impact system logs can have on a forensics investigation based on the type of incident. Because system logs can track not only events that occur but pin point the time they happened, they can be extremely useful for determining cause and source of insider file deletion. While a challenging prospect, used in conjunction with access logs and a role based user management system, system logs could potentially have the greatest impact in this area.

While system logs provide a great deal of information with ongoing server events, they may be useful for detecting network intrusion, however such incidents might be better examined at the network layer. System logs can also have an impact on detecting malware that may have inadvertently been installed on the server via deliberate or accidental means, however examination of the file system may yield more insight than logs when considering malicious code.

## File Systems

Hackers are increasingly using a technique, known as steganography, to trick internet users and smuggle malicious payloads past security scanners and firewalls. Newman (2017). The term ‘Steganography’ refers to ‘covered writing’ and encompasses methods of transmitting secret messages through innocuous cover carriers in a manner that their existence is undetectable. Johnson and Jojodia (1998). Malicious code or malware often uses covert means to hide within a file systems application code. Operating System (OS) file systems are often used by attackers to their advantage in embedding such code within a sever.

### Metadata

Most computing systems have some type of long-lived data storage that may be examined for evidence. Buchholz and Spafford (2004). Metadata contained in file system snapshots can provide insight in a forensics investigation including but not limited to unauthorized deletion and modification of files. In partnership with digital forensics software and scanning tools, file systems can provide information on potential malware software, compliment auditing data provided via system logs and access management systems, and help trace back activity that previous occurred with a subset of information or data. It is important to note that the information available in the file system alone would not be sufficient in order to track back to a source user. Correlation with an access management system comparing time stamps and other attributes could help verify this level of data, but it may be a tedious process. Buchholz & Spafford (2004).

### Extracting Data

Forensics researchers have to be careful on how information is extracted from a file system and need to be able to make a copy of the data while maintaining its integrity for further examination. This is often crucial in situations where a forensics team may have limited time in order to capture data from a compromised system in the case of hard disks or other storage devices attached to the server. Special forensics tools exist to aid forensics personnel in extracting data from file systems including disk and data capture tools, file analysis tools, network forensics tools, and database forensics tools.

### Impact and Usefulness in Forensics Investigations

File systems can provide a lot of useful data for forensics investigators and are especially useful when researching malware infections including cause and spread. Metadata captured in file systems can be helpful in determining an electronic fingerprint and may be able to provide insight into malicious insider activities such as file deletion.

**Table 2: File Systems Matrix**

|   | **Highest Impact** | **High Impact** | **Medium Impact** |
| --- | --- | --- | --- |
| **Network Intrusion** |  |  | \* |
| **Malware Detection** | \* |  |  |
| **Insider file deletion** |  | \* |  |

Table 2 identifies the greatest impact on forensics investigation with regard to malware detection and insider file deletion as discussed. Remaining the lowest in priority or impact are those incidents involving network intrusion, whereby file systems may not provide the greatest impact when compared to the other sources documented in this paper. Network intrusion is better analyzed using IDS or directly examining log files, however file systems may provide complimentary evidence in these scenarios.

## Intrusion Detection and Prevention Systems

Earlier in this paper, logs were discussed in terms of their relevance to various security incidents. Another means to providing more transparency into a system where various incidents may have happened is through the use of an Intrusion Detection System (IDS). Intrusion Detection Systems (IDS) come in various forms and provide different functionality. Host based systems are by their very name concerned with the host it is attached to. When the first intrusion-detection tools were designed, the target environment was a mainframe computer, and all users were local to the system considered. Debar, Dacier, and Wespi (1999). Host based IDS therefore evolved from this mentality to their current form which are typically software based and reside on a single host or computer. Network based IDS on the other hand are used to capture and analyze packets of data sent across an entire network. Another term called Intrusion Prevention Systems (IPS) is an IDS that also performs actions based on a set of criteria that alert the system based on suspicious traffic. The terms IDS and IPS are often interchangeable, however in a forensics investigation, the aftermath of an incident is usually what is of concern and any data captured will help support analysis.

### IDS Alerts and Evidence

Alarms or alerts provided by an IDS can provide forensic investigators clues and information on the source of any given incident. A network IDS may be able to provide greater insight into external attacks on the network itself or may point the analysis in the right direction to look for the correct log files that could back up a hypothesis. Alarms and alerts are designed to trigger when incidents occur based on known patterns or signatures, or based on anomalies (those behaviors which are seen to be outside the norm). As Tan, Thompson, and Ruighaver (2000) clearly articulate, the ultimate goal of intrusion detection is to “identify, preferably in real-time, unauthorized use, misuse, and abuse of computer systems by both system insiders and external penetrators.” They go on to further solidify this purpose by stating that in the case of anomaly intrusions, intrusion detection is based on the idea that the anomalies that may surface in a system are symptoms indicating illegal, intrusive or criminal activity. While detecting, blocking and alerting through alarms or other system-based triggers is one of the main tasks carried out by and IDS, an additional feature of such systems involves file carving. Khalil (2015) describes file carving as the process of extracting files from network data streams, which can provide significant forensic benefits in detecting malware staging, data collection and exfiltration.

### Impact and Usefulness in Forensics Investigations

While system log files as covered earlier, provide an excellent source of timestamped event messages, Intrusion Detection Systems provide investigators with more information at another layer of the system. Network based IDS provide the greatest insight into network intrusions as they can capture anomalies in traffic, identifying source and target destinations, and overall patterns that may lead to a more in-depth look at other logs as part of the investigation.

**Table 3: IDS Matrix**

|   | **Highest Impact** | **High Impact** | **Medium Impact** |
| --- | --- | --- | --- |
| **Network Intrusion** | \* |  |  |
| **Malware Detection** |  | \* |  |
| **Insider file deletion** |  |  | \* |

IDS can also be useful in detecting malicious code that has entered the system from an external source and provide another lens into the incident for further analysis by the forensics team. Incidents of file deletion may not be as easily determined from IDS usage alone, but in combination with other tools and techniques, data captured may have some value here also.

## Memory Images

During a digital forensics investigation, those carrying out the analysis on various data sources may have a limited time to capture important data from volatile sources such as memory. A memory image is essentially a snapshot of all information captured in a systems Random Access Memory (RAM) that is by its very nature volatile. In a typical computer system, as soon as it is shut down, contents within memory are destroyed. In addition to this, memory is not in a static state and is forever changing depending on user interactions, services and other application calls within the system. It is therefore essential that a forensics expert can recover a memory image as quickly as possible before any important evidence is modified or destroyed.

### Volatility and Capture

Sutherland, Evans, Tryfonas, & Blyth (2008) describe volatile date as vital in determining criminal activity. Such data may contain passwords used for encryption, indications of anti-forensic techniques, and memory resident malware which would otherwise go unnoticed by the investigator. In terms of type of incident (network intrusion, malware detection or insider file deletion), all of the these could be greatly impacted depending on the type of data left behind within a memory image. Amari (2009) details the various types of data that can potentially be found in volatile memory. In her article on recovering and analyzing such data, she highlights processes, open files and registry handles, network information, passwords and cryptographic keys, unencrypted content, hidden data, and malicious code. Her article demonstrates the importance of this data source along with the challenges of capturing and preserving it.

There are many different tools forensics personnel can use to extract memory images. First and foremost are timing as stated above and also integrity. While extracting data in a timely manner is important when working with volatile data, without properly carrying out the extraction process and preserving the integrity of the data, any evidence captured will not be as useful to the overall investigation and could jeopardize the entire process. LIME (Linux Memory Extractor) is one of the more popular tools used by investigators in Linux based systems. Another tool that has been around for many years is Memdump, a free cross-platform tool that can create bit-by-bit copies of volatile memory. Other tools include KnTTools, FATKat, and WMFT. Amari (2009).

### Impact and Usefulness in Forensics Investigations

Unlike traditional storage of data such as file systems on hard disks or other physical medium, memory contains much information that will never be persisted to such devices. Information such as unencrypted data and code that can be used in a forensics investigation are paramount to any analysis. Amari (2009) brought up an excellent point regarding residual data from malware that may only be available in memory and not persisted to other storage. This data could provide investigators means to detect advanced in-memory malicious code, its purpose and impact on the system at large.

**Table 4: Memory Images Matrix**

|   | **Highest Impact** | **High Impact** | **Medium Impact** |
| --- | --- | --- | --- |
| **Network Intrusion** |  | \* |  |
| **Malware Detection** | \* |  |  |
| **Insider file deletion** |  |  | \* |

While table 4 provides an overview on the impact memory images can have to different investigations, it’s important to note that data retrieved from memory could be extremely important to all three. Taking network intrusions as the next type of incident, memory can house all kinds of useful information from active listening ports and current connections. While insider file deletion is ranked the lowest in the above matrix, useful information could also be garnered to help with this type of investigation in the form of open files and registry handles. Memory images may be one of the more challenging data sources to retrieve due to its highly volatile nature, however it may yield some of the greatest insight into investigations of all kinds.

## Conclusion

Each of the four data sources documented in this paper are essential to any given forensics investigation involving incidents of network intrusion, malware detection and insider file deletion. It is challenging to silo any of these sources under any of the given scenarios mentioned, however the matrixes provided under each data source gives a best estimate in terms of prioritizing within each incident. Some of the tools and techniques were also touched on, however as hackers continue to find new ways to commit crimes through computer systems, forensics tools, methods, and process will also continue to evolve.

Prioritization itself may also change over time as newer methods of data extraction and methods of capturing evidence from systems that have been subject to an attack of breach. One of the most significant considerations in any investigation will remain the preservation and integrity of data captured in order to properly support a forensics investigation. This paper focused mainly on the data sources themselves and not as much on the processes or long-term persistence and preservation, however these must be considered within any forensics investigation and analysis, otherwise the data sources themselves will provide little value.

## References

Amari, K. (2009). Techniques and tools for recovering and analyzing data from volatile memory. _SANS Institute InfoSec Reading Room_.

Bergeron, J., Debbabi, M., Desharnais, J., Erhioui, M. M., Lavoie, Y., & Tawbi, N. (2001). Static detection of malicious code in executable programs. _Int. J. of Req. Eng_, 2001(184-189), 79.

Brandom, R. (2017). The FTC is looking into the Equifax breach. The Verge. Retrieved from https://www.theverge.com/2017/9/14/16306872/equifax-breach-ftc-probe-lawsuit-vulnerability

Buchholz, F., & Spafford, E. (2004). On the role of file system metadata in digital forensics. _Digital Investigation_, 1(4), 298-309.

Cohen, M., Garfinkel, S., & Schatz, B. (2009). Extending the advanced forensic format to accommodate multiple data sources, logical evidence, arbitrary information and forensic workflow. _Digital Investigation_, 6, S57-S68.

Conrad, S. H., Durán, F. A., Conrad, G. N., Duggan, D. P., & Held, E. B. (2009, August). Modeling the employee life cycle to address the insider threat. In _Proc. 27th Int’l Conference of Sys Dynamics Society_. Albuquerque, NM.

Debar, H., Dacier, M., & Wespi, A. (1999). Towards a taxonomy of intrusion-detection systems. _Computer Networks 31_ (1999) 805-822.

Johnson, N. F., & Jajodia, S. (1998, September). Steganalysis: The investigation of hidden information. In _Information Technology Conference_, 1998. IEEE (pp. 113-116). IEEE.

Khalil, G. (2015). An Overview to Forensic Enterprise Architecture Design. SANS Institute InfoSec Reading Room. Retrieved from: https://www.sans.org/reading-room/whitepapers/forensics/ids-file-forensics-35952

Motiee, S., Hawkey, K., & Beznosov, K. (2010). Do windows users follow the principle of least privilege?: investigating user account control practices. In _Proceedings of the Sixth Symposium on Usable Privacy and Security_ (p. 1). ACM.

Mukherjee, B., Heberlein, L. T., & Levitt, K. N. (1994). Network intrusion detection. _IEEE network_, 8(3), 26-41.

Newman, L., H. (2017). Hacker Lexicon: What is steganography? _Wired_. Retrieved from: https://www.wired.com/story/steganography-hacker-lexicon/

Sadowski, G. (2010). Using logs for forensics after a data breach. _Network World_. Retrieved from: https://www.networkworld.com/article/2193990/tech-primers/using-logs-for-forensics-after-a-data-breach.html

Sutherland, I., Evans, J., Tryfonas, T., & Blyth, A. (2008). Acquiring volatile operating system data tools and techniques. _ACM SIGOPS_ Operating Systems Review, 42(3), 65-73.

Tan, K. M., Thompson, D., & Ruighaver, A. B. (2000). _Intrusion detection systems and a view to its forensic applications_. Technical report, Department of Computer Science, University of Melbourne, Parkville 3052, Australia, year of publication unkown. URL http://www. securityfocus. com/data/library/idsforensics. ps.

Tanenbaum, A. S. (2009). Modern operating system. Pearson Education, Inc.
