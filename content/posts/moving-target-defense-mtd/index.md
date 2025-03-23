---
author: "icarnaghan"
title: "Moving Target Defense (MTD)"
date: 2018-02-19
categories: 
  - "cybersecurity"
tags: 
  - "academic-papers"
  - "csec-670"
  - "featured"
---

Organizations continue to struggle with policies and processes to effectively secure their infrastructure to protect their information assets and intellectual property. In recent years, we have seen the increase of cyber-attacks and breaches to the point that they have become common news worldwide. As systems have grown in complexity with increased capacity to store large amounts of data, so to has the appeal of targeting such systems by cyber criminals. Traditional approaches of defense including signature-based detection, behavioral-based detection, and defense in depth strategies are not enough to protect against advanced distributed attacks and zero-day attacks. Current technologies used to detect traffic, whether packet-based, time-based, or behavior-based, can provide some level of defense. Unfortunately, however as our tools and techniques improve, so too do the accuracy and advancements in sophisticated attackers.

Some of the more sophisticated attacks include Advanced Persistent Threats (APTs) and Distributed Denial of Service (DDoS). DDoS can cause a massive impact financially on an organization in terms of availability. A DDoS attack by definition is an attack intended to cause a service to become unavailable or unusable (Desai, Patel, Somaiya, & Vishwanathan, 2016). They are sometimes referred to as SYN Flood attacks, caused through exploitation of the TCP protocol. The attacker sends a large number of TCP/SYN packets using a forged address. Because of this, the destination server is unable to successfully establish a proper connection due to the source being unreachable. These types of attacks can also tarnish their reputation to the point of putting them out of business, or severely crippling operations. APTs on the other hand are security threats that use advanced techniques to hide their attack from the target. They are commonly used to target specific information in high-profile companies and governments. APTs usually follow a long-term strategy of attack in order to gather information from the breached system. One of the most complex APTs in recent years was the Stuxnet computer worm, which targeted Iran’s nuclear program (Levi, 2012).

One of the things that these two types of threats have in common is their ability to bypass traditional defenses by leveraging an arsenal of diverse and sophisticated cyber tools. Malicious actors can use networks of compromised and remotely controlled hosts, known as botnets, to execute a number of different cyberattacks and engage in criminal or otherwise unauthorized activities (Albanese, Jajodia, & Venkatesan, 2018). In order to meet these challenges head on, business organizations must adapt and implement a comprehensive defense strategy to combat threats that continue to evolve. Traditional security hardening measures have focused on reducing the size of the attack surface (Zhuang et al., 2013). Topology-aware botnets maintain their stealth by using commonly placed detectors and architecture to their advantage in order to evade detection, while other types of botnet achieve resilience through anti-signature approaches.

An emerging approach in cybersecurity called Moving Target Defense (MTD) has made a lot of impact in recent years as techniques continue to evolve. The idea behind MTD is analogous to that of having to reset a password every 90 day. The password that was being targeted has ‘moved’ or changed, further complicating the process for the attacker and better defending the user credentials. In an MTD strategy, attributes of the network become dynamic, instead of static, obfuscating the attack surface. The concept of MTD was popularized in 2011 by Jajodia, Ghosh, Swarup, Wang, and Wang in their publication titled, “Moving target defense: creating asymmetric uncertainty for cyber threats”. Since then much research has taken place in this field and it continues to evolve. Newer technologies including container orchestration coupled with cloud platforms, enable and help drive innovation in building dynamically changing attack surfaces. MTD essentially shifts the paradigm of an unfair asymmetric advantage that the attacker has traditionally had, to that the defender by creating uncertainty.

## Moving Target Defense Research and Development

The premise behind Moving Target Defense (MTD) is that of a dynamic or constantly changing network in terms of configuration in order to increase the difficulty of intrusion as well as maintain illegally acquired privileges for long (Zhuang et al., 2013). While the concept of MTD has been around for several years, it is an emerging methodology that continues to break ground within the cybersecurity community. It provides a great deal of optimism for combatting more advanced threats and botnets by creating asymmetric uncertainty. There are three types of MTD, Network level, host level, and application level. Each of these are designed to dynamically move the attack surface based on a number of configuration changes and are listed in the table below.

### MTD Types

| **Network Level MTD** |   - IP Hopping (Changing host IP address) - Obfuscating Port Traffic through random assignment of port numbers, inflated number of non-valid ports - Spoofing host information such as Operating System types and versions through random network services   |
| --- | --- |
| **Host Level MTD** |   - Changes to the host and Operating System level resources - Changes to naming and configurations   |
| **Application Level MTD** |   - Address Space Layout Randomization (ASLR) involving randomly arranging memory layout - Changes in application types, versioning, and routing through different hosts - Alterations to the programming languages used, compiling processes, and alteration to the source code itself.   |

Over the years, there have been a number of strategies for integrating MTD successfully within an enterprise level network. These strategies have involved a combination of host, network and application approaches in order to move the attack surface effectively, preventing or slowing down attackers. More importantly MTD has provided a way for the organization to protect itself against the common ‘reconnaissance’ phase a sophisticated attack pattern would follow. MTD continues to evolve as research and technologies advance in this area. Some of the major benefits of MTD includes detection techniques, scalable security, orchestration, and business innovation (Burshteyn, 2017). Each of these are highlighted below.

### Detection Techniques

Much of the work involved in defense and protection today involves a framework of detection and mitigation. MTD shifts this focus to moving targets in order to make it more difficult for the attacker. Not only does this cause a huge disadvantage to the attacker, it also provides a means for protecting the infrastructure against unknown threats.

### Scalable Security

MTD also provides better opportunities for ‘scalable’ security. Traditionally infrastructure grows over time and inadvertently increases the overall attack surface. As the network increases in sophistication with more potential vulnerabilities or attack surface, more resources must be poured into security infrastructure. With the dynamic nature of MTD, the attack surface is essentially decreased in size by its very nature of remaining in flux. This asymmetric switch enables the organization to remain ahead of defense while scaling out their infrastructure using dynamic techniques.

### Orchestration

The continued adoption of cloud technologies and containerization has led to new possibilities for developing dynamic infrastructure. The idea behind containers is similar to traditional virtual machines whereby an environment is created in a reusable domain that can be easily destroyed and provisioned at will. Newer technologies have embraced the concept of infrastructure as code including Amazon Web Services (AWS) CloudFormation, and other third-party frameworks such as Terraform. These tools give the organization a means to adapt quickly and move resources is needed. If a window is broken, move your data and rotate your keys. MTD also increases the value of existing traditional tools and methods since it lends itself well to orchestration via APIs (Burshteyn, 2017).

### Business Innovation

Combining the various techniques and processes needed for an effective MTD strategy not only strengthens existing security posture, but also encourages innovation and an embrace of these technologies. Many organizations are moving much of their infrastructure to the cloud. Being able to leverage dynamic environments, newer ways of handling configuration management, and building out infrastructure as code methodologies will keep these organizations innovative. Organizations like Polyverse are already providing consulting and services to assist with recycling containers, compiler-based scrambling via polymorphic Linux, and they also provide a full suite of MTD tools (“Moving Target Defense, Code Scrambler, & Container Cycler,” n.d.). As technologies mature, MTD becomes more feasible for not only larger enterprises, but also smaller businesses ready to leverage these frameworks into their security models.

## How Organizations use MTD

As mentioned earlier, companies like Polyverse are already starting to offer third party frameworks, tools and consulting solutions to organizations. As research in the field increases, so too does the recognition of applicable use of MTD in the enterprise. More recently (Albanese et al., 2018) laid out a framework for defending specifically against botnets that employ stealth techniques to remain undetected. In their publication, they discussed MTD in terms of approaching a multifaceted problem including detector placement, bot identification, and botnet lifetime. The purpose of this publication was to examine current approaches and suggest a process of implementing an effective and scalable MTD solution.

### Detector placement

Currently business organizations perform an assessment of their infrastructure in order to determine those areas that could potentially cause the most harm if a successful breach was to occur. Due to the fact that it would not be possible or cost beneficial to place detectors in all endpoints within the network, decisions have to be made on where to provision them. To address this problem, organizations can adopt heuristic detector placement strategies that select subnets of a network’s nodes based on their centrality. (Albanese et al., 2018) suggest an MTD approach, altering the placement of detectors can introduce uncertainty and force attackers to perform additional, potentially detectable actions in order to maintain a botnet.

### Bot Identification

In their paper, (Albanese et al., 2018) also discuss strategies that business organizations can use for detecting bots. They presented a novel network-based detection scheme called DeBot, which can identify traffic flows potentially associated with data exfiltration attempts. In their research, results indicated that DeBot was more effective in detecting botnet activity and mapping out the botnet’s architecture than existing solutions.

### Botnet Lifetime

(Albanese et al., 2018) also proposed a strategy to eradicate a botnet from a network by using a solution called Reinforcement Learning (RL). The compared their solution to other approaches including a simple static strategy, centrality strategy, and a myopic strategy, where placement changes based on short-term benefits from continuous feedback. Their RL approach outperformed the rest. Because MTD is continuing to evolve, academic research like this will only continue to benefit organizations with newer and more accurate defenses within their arsenal of security tools and processes.

## Organizations Supporting MTD

In 2017, Cryptonite NXT published a white paper on Moving Target Defenses and network microsegmentation. The paper shared information on how organizations could use these highly innovative technologies to fit with their environments and complement existing investment in cyber security tools. (“An Introduction to Moving Target Cyber Defense (MTD) for CISOs,” 2017). Other organizations like Morphisec are deeply involved with MTD strategies and provide various services that enable organizations to implement a dynamic approach to their infrastructure and security. Morphisec provide endpoint threat protection, a VDI security solution, and also focus on ransomware attacks and prevention strategies (“What we do - Endpoint Security Reinvented,” n.d.).

Larger, well known organizations like Intel, IBM and Microsoft are also taking notice. Intel and Microsoft have been working to use Controlflow Enforcement Technology (CRT) to combat Return Oriented Programming (ROT) attacks (Jarrous, 2016). More recently IBM has been pushing its Anti-ROP Moving Target Defense Technology within its Haifa research division.

### Polyverse Case Study

In 2017, a test case was proposed to Polyverse, which agreed to allow a full penetration test against its production servers as well as access to logs to determine how well detection and responses were carried out (ISACA, 2017). As mentioned earlier, Polyverse is an organization that provides MTD services to businesses, prevention of zero-day attacks, and security hardening of systems. In this real-life example of MTD at work, their live web application Content Management System (CMS) was targeted. The study conclusively demonstrated the resiliency of the MTD defense technologies. None of the attacks resulted in remote access to sensitive information or the ability to modify server\-side data. The penetration test that was used was unable to force the servers to act in an unintended manner or disclose any sensitive information. Even if more time was to be given in this test scenario, the process or re-imaging servers in their MTD approach would have meant any progress made in an attack was effectively undone (ISACA, 2017).

### Morphisec Case Study

Morphisec recently worked with a high-tech manufacturing organization to successfully integrate and implement an MTD framework that would better protect intellectual assets (Morphisec, 2017). The CIO worked closely with Morphisec to plan for a security approach that would better protect against advanced threats and in-memory attacks, which neither their anti-virus solutions nor newer installed AI-based protection could fully protect against. A security breach within the organization could potentially be catastrophic in terms of their market position as well as their overall business model. The organization has since reported back that the Morphisec product suite has operated flawlessly, significantly reducing the company’s attack surface with zero associated maintenance. According to Morphisc, they are now protected from both commodity threats as well as advanced attacks. MTD has provided a scalable and effective solution.

## Role of the Federal Government

The U.S. Federal cybersecurity market is estimated to reach $22 Billion by 2022, with infrastructure hardening segment to grow up at a steady Compound Annual Growth Rate (CAGR) of 12% (“U.S. Federal Cybersecurity Market Forecast 2017-2022,” 2018). As advanced threats become more prevalent while organizational infrastructure continues to grow in complexity, an approach to scalable yet cost effective methods is needed. The Federal Government has been committed to research in MTD for a number of years. It is essential now more than ever before to research and develop cost-effective solutions that can be ready to combat these threats, while not significantly increasing the expense of such defensive systems. The government is also interested in discouraging the use of ‘bolt-on’ security processes, and MTD can provide an integral path.

### MTD Research Efforts

While MTD is still a relatively new concept in the security worlds and many tools, techniques, and processes are only now emerging, the Federal Government has funded MTD research since 2009. In 2011 the White House, in cooperation with Networking and Information Technology Research and Development (NITRD) Program released the report Trustworthy Cyberspace: Strategic Plan for the Federal Cybersecurity Research and Development Program National Symposium on Moving Target Research (“Moving Target Research,” n.d.). In this plan Moving Target (MT) was outlined as a research thrust. In the paper, MT technologies were highlighted as enablers for creating, analyzing, evaluating, and deploying mechanisms and strategies that are diverse and continually shift and change over time to increase complexity and cost for attackers. The definition continued to call out limiting of exposure of vulnerabilities and opportunities for attack, and increased overall resiliency (Executive Office of the President National Science and Technology Council, 2011). Until recently, there had not been a single venue where this work was presented and published. The National Symposium on Moving Target research has changed this routinely calling for research papers.

### Benefits & Drawbacks of Government Efforts

As mentioned above, while the Federal Government has made efforts in the area of Moving Target Defense (MTD), research efforts have been scattered. On the Moving Target Defense homepage of the Department of Homeland Security, the information provided is dated and categorized as ‘archive content’. Most of the information available is second-hand and references back to the 2011 Whitehouse publication.

When searching for more information on the National Symposium on Moving Target Research, it was difficult to ascertain exactly what federally sponsored research has been carried out. On the Cyber-Physical Systems Virtual Organization website that houses the call for papers for National Symposium on MT Research, the page looks dated and references 2012 events. Upon further research it appears that the ACM Workshop on Moving Target Defense is very much ongoing and involves researchers from academia, government, and industry. The workshops report on the latest research efforts on MTD and have productive discussion and constructive debate on the topic (“Fourth ACM Workshop on Moving Target Defense (MTD),” n.d.). In addition to this, there have been various Small Business Innovation Research (SBIR) and Small Business Technology Transfer (STTR) grants awarded by the Federal Government over the years for MTD research.

While the drawback of Federal Government involvement in the advancement of MTD has proven to be slow and disparate in the past, it continues to invest substantially into this field and its efforts will no doubt benefit both federal agencies and private sector business. Through collaboration with the academic and professional security communities, MTD research will enable the development of newer technologies, processes, and techniques that can be used to not only keep up with ever changing threats, but to remain several steps ahead. The process of moving the asymmetric advantage to that of the defender away from that of the perpetrator, will only help foster these newer approaches through collaborative peer research.

### Real-world examples of Government Support

In addition to some of the efforts already mentioned earlier including SBIR, STTR grants for research, the National Symposium on MTD, and the ACM Workshop on MTD, the Federal Government has also funded other initiatives in the defense department over the years. In 2014, the Air Force released a solicitation for the development of a command and control capability that could orchestrate Moving Target Defense across the entire enterprise (Cheng, 2014). The Federal Government has been concerned with seeking out strategies that will enable a move of their cyber defenses from traditional static approaches to dynamic MTD frameworks. Other initiatives have been ongoing overtime in collaboration with private and academic groups. Cyber Operations, Analysis, and Research has been collaborating with the Air Force Research Lab (AFRL) on MTD. Research has involved multiple OS rotational environments, dynamic application rotation environments, and stream splitting MTD (“Moving Target Defense,” 2018).

The National Institute of Standards and Technology (NIST) has also been involved with various MTD initiatives over the years. In a paper published by NIST in 2013, a preliminary design was proposed for computer networks to combat an attacker’s asymmetric advantage. Several experiments were conducted to study the effects of randomly adapting one aspect of the system in reducing the attacker’s success likelihood (Zhuang et al., 2013). Their findings revealed that even with less perfect detectors, significant improvements were show paving the way for simple and intelligent MTD systems.

In addition to other efforts, the Federal Government is making an impact through the Federal Cybersecurity R&D Community, which has called for the development of various MTD technologies. These include non-persistent execution environments, randomized execution of code, randomized network and host identities, randomizing compilers, dynamic address spaces, and automated patch systnesis and installation (Vagoun, 2015).

Finally, another area that the Federal Government continues to have an impact on real-world application of cybersecurity approaches related to MTD is within one of its biggest initiatives, the Continuous Diagnostics and Mitigation (CDM) program by the Department of Homeland Security. In 2017, DHS program managers were tasked with redesigning the CDM program into a new initiative called CDM DEFEND, which stands for Dynamic and Evolving Federal Enterprise Network Defense (Boyd, 2017). CDM is already widely used across government agencies and also serves as a blueprint that can be used in the commercial world. It is clear that efforts are increasing in the areas of Moving Target Defense and dynamic approaches to security backed by the Federal Government. This is an area that will only continue to grow and become more prominent in the years ahead.

## Conclusion

Moving Target Defense is an emerging cybersecurity approach that has been moving closer to the forefront in the way organizations handle security design and operations. It has embraced newer cloud-based technologies including infrastructure as code, containers, and orchestration. The idea of moving the advantage of asymmetric attacks to that of the organization away from that of the perpetrator is truly a compelling argument for research and development. In the private sector, there are already examples of where MTD is making an impact. The Federal Government was slow to initially support MTD, however it is clear that in recent years, this has become pivotal in their cybersecurity strategy.

This field will continue to emerge as newer technologies, tool, and techniques come to light that can support an effective MTD approach. The idea of dynamic defenses through MTD is essential if organizations and government are to keep up and become less reactive and more proactive in their security posture. Through ongoing collaboration among the research, government and private sectors, the advancement of MTD will continue to evolve, making more scalable and cost-effective defense systems that can be better prepared against advanced threats.

Albanese, M., Jajodia, S., & Venkatesan, S. (2018). Defending from Stealthy Botnets Using Moving Target Defenses. _IEEE Security & Privacy_, _16_(1), 92–97. 10.1109/msp.2018.1331034" target="\_blank" rel="noopener noreferrer">https://doi.org/10.1109/msp.2018.1331034

An Introduction to Moving Target Cyber Defense (MTD) for CISOs. (2017). Retrieved February 1, 2018, from https://info.cryptonitenxt.com/resources#whitepaper

Boyd, A. (2017, October 30). Government’s biggest cybersecurity program is evolving. Retrieved February 1, 2018, from https://www.fifthdomain.com/civilian/dhs/2017/10/30/governments-biggest-cybersecurity-program-is-evolving/

Burshteyn, M. (2017, March 20). Moving Target Defense — recent trends. Retrieved February 1, 2018, from https://blog.cryptomove.com/moving-target-defense-recent-trends-253ce784a680

Cheng, J. (2014, July 24). Air Force gets a move on dynamic cyber defense -- Defense Systems. Retrieved February 28, 2018, from https://defensesystems.com/articles/2014/07/24/air-force-cyber-moving-target-defense.aspx

Desai, M., Patel, S., Somaiya, P., & Vishwanathan, V. (2016). Prevention of Distributed Denial of Service Attack using Web Referrals: A Review. _International Research Journal of Engineering and Technology_, _3_(4), 3.

Executive Office of the President National Science and Technology Council. (2011). _Trustworthy cyberspace: Strategic plan for the federal cybersecurity research and development program_. _Trustworthy cyberspace: Strategic plan for the federal cybersecurity research and development program_ (p. 36). Retrieved from https://www.nitrd.gov/SUBCOMMITTEE/csia/Fed\_Cybersecurity\_RD\_Strategic\_Plan\_2011.pdf

Fourth ACM Workshop on Moving Target Defense (MTD). (n.d.). Retrieved February 1, 2018, from http://mtd-2017.mit.edu/

ISACA. (2017). _Moving Target Defense Against Web Application Attacks_. _Cybersecurity Nexus_ (p. 30). Retrieved from https://www.isaca.org/Knowledge-Center/Research/Documents/Polyverse-Case-Study\_res\_eng\_0617.pdf

Jarrous, A. (2016, September 1). Anti-ROP: A Moving Target Defense. Retrieved February 1, 2018, from https://securityintelligence.com/anti-rop-a-moving-target-defense/

Levi, R. (2012). Stuxnet: Advanced Persistent Threat. Retrieved February 1, 2018, from https://www.cmpod.net/all-transcripts/stuxnet-the-malware-that-struck-the-iranian-nuclear-program-text/

Morphisec. (2017). _Staying Ahead of Attackers with Moving Target Defense_ (p. 2). Retrieved from https://www.morphisec.com/wp-content/uploads/2017/10/Morphisec-High-Tech-Manufacturing-Case-Study\_Final.pdf

Moving Target Defense. (2018). Retrieved February 28, 2018, from https://coar.risc.anl.gov/research/moving-target-defense/

Moving Target Defense, Code Scrambler, & Container Cycler. (n.d.). Retrieved February 28, 2018, from https://polyverse.io/how-it-works.html

Moving Target Research. (n.d.). Retrieved February 1, 2018, from https://cps-vo.org/group/mtrs

U.S. Federal Cybersecurity Market Forecast 2017-2022. (2018, February 12). Retrieved February 1, 2018, from https://www.marketresearchmedia.com/?p=206

Vagoun, T. (2015). _Challenges of Engineering Cybersecurity: a Government Perspective_ (p. 7). National Coordination Office for Federal Networking and IT R&D Program. Retrieved from https://www.naefrontiers.org/File.aspx?id=50754

What we do - Endpoint Security Reinvented. (n.d.). Retrieved February 1, 2018, from https://www.morphisec.com/what-we-do/

Zhuang, R., Zhang, S., Bardas, A., DeLoach, S. A., Ou, X., & Singhal, A. (2013). Investigating the application of moving target defenses to network security. In _2013 6th International Symposium on Resilient Control Systems (ISRCS)_. IEEE. 10.1109/isrcs.2013.6623770" target="\_blank" rel="noopener noreferrer">https://doi.org/10.1109/isrcs.2013.6623770
