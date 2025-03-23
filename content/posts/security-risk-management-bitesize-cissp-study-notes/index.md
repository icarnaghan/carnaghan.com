---
author: "icarnaghan"
title: "Security Risk Management - Bitesize CISSP Study Notes"
date: 2019-09-03
categories: 
  - "cybersecurity"
---

Security Risk Management is the first domain of the CISSP. These are some notes highlighting areas of study for this domain and are by no means a comprehensive set of materials for preparing for this certification. The content below is what I have used to better prepare for this domain. Before reviewing this section, if you haven't already taken Kelly Handerhan's CISSP course, I would highly recommend spending some time going through it. It is by far the most engaging and relevant video series I've seen for CISSP study prep. In the first domain she covers a slide called the tenants of secure design, which is also very relevant here. At a minimum, make sure you are familiar with concepts she covers here including risk analysis, defense in depth, fail safe, KISS (Keep it Simple Stupid), completeness of design, open design, redundancy, separation of duties, mandatory vacations, job rotation, and others.

## The CIA Triad

Spend time understanding the difference between overt and covert, see data hiding and steganography. For confidentiality also consider the state of the data (at rest, in process, or in transit) and understand the different methods of protection available at each. An analysis of different data sources used in a forensics investigation gives a good overview of the importance of preserving the integrity of data used for evidence. When thinking about availability, spend time to understand Service Level Agreements (SLAs), Mean Tolerable Downtime (MTD), Recovery Time Objective (TRP) vs Recovery Point Objective (RPO), Mean Time Before Failure (MTBF) and Mean Time To Repair (MTTR).

| Confidentiality | Integrity | Availability |
| --- | --- | --- |
| Overt (Cryptogaphy & Masking)   Covert (Steganography)   States (At rest (Encryption AES 256), in process, in transit (SSL/TLS IPSEC)) | System Integrity (code injection, input validation)   Data Integrity (CRCs, Checksums, Message Digests, Hashes, MACs)   Least privilege | SLAs   MTD/RTO/RPO   MTBF/MTTR   Support Requirements |

## IAAA

Understand Discretionary Access Control (DAC) vs Mandatory Access Control (MAC). Consider SELinux when thinking about MAC. Roles based access (RBAC) and Rules Based Access Control (RuBAC) are also important to grasp. Think firewalls / rules for RuBAC.

| Identity and Authenticity | Authorization | Accountability |
| --- | --- | --- |
| Identity is claim and validation of an entity's identity claim is authentication   Authentication methods include Certificates, Forms/Credentials, Tokens (SSO), Smart cards, Biometrics | DAC, MAC, RBAC, RuBAC   Authorization Requirements | Tracing an action to a subject / Auditing   Identity, action, object on which action performed, timestamp |

In addition to understanding CIA and IAAA, you should also understand Nonrepudiation, least privilege & need to know, subjects and objects, and defense in depth. You should also understand Risks, Threats, and Vulnerabilities and Confusion over Terminology.

## Legal and Regulatory Concepts to Understand

Understand the different legal systems: common law, civil law, and religious / customary. Common law places an emphasis on cases won in the past, whereas civil law is codified. Don't confuse civil legal system with civil laws, listed below. You should also understand the difference between Due Care and Due Diligence.

> Think of Due Care as the prudent person rule (doing the right thing), and Due Diligence as the formalization of Due Care in an organization (such as policies). Gross Negligence in contrast is the opposite of Due Care.

Spend time on the different laws, damages, types of evidence listed below. You will need to know the various definitions associated with computer crime and privacy. Finally spend time on the Council of Europe Convention on Cybercrime.

- **Laws**: Criminal, Civil, Administrative
- **Damages**: Statutory, Compensatory, Punitive
- **Evidence**: Real, Direct, Circumstantial, Corroborative, Hearsay, Secondary
- **Computer Crime & Intellectual Property**: Trademark, Patent, Copyright, License, Trade Secret
- **Privacy**: EU Data Protection Directive, OECD, EU-US Safe Harbor
- **International Corporation**: Council of Europe Convention on Cybercrime

## Ethics

Ethics is covered quite lot in this domain. Take time to memorize the ISC Code of Ethics, Computer Ethics Institute 10 Commandments of Computer Ethics, and IAB's Ethics and the Internet below.

| ISC Code of Ethics (Preambles, Canons, Guidance) | Computer Ethics Institute | IAB's Ethics and the Internet |
| --- | --- | --- |
| Protect society, the commonwealth, and the infrastructure.      Act honorably, honestly, justly, responsibly, and legally.      Provide diligence and competent service to principals.      Advance and protect the profession | Thou shalt not:   \- use a computer to harm other people.   \- interfere with other people's computer work.   \- snoop around in other people's computer files.   \- use a computer to steal.   \- use a computer to bear false witness.   \- copy or use propriety software for which you have not paid.   \- use other people's computer resources without authorization or proper compensation.   \- appropriate other people's intellectual output.   Thou shalt:   \- think about the social consequences of the program you are writing or the system you are designing.   \- always use a computer in ways that ensure consideration and respect for your fellow humans. | According to the IAB, the following practices would be considered unethical behavior if someone purposely:      Seeks to gain unauthorized access to the resources of the Internet      Disrupts the intended use of the Internet   Wastes resources (people, capacity, computer) through such actions      Destroys the integrity of computer-based information      Compromises the privacy of users |

## Information Security Governance

Understand the different types of documentation used within security governance. They should mirror real-world situations and provide direction on implementing the correct actions. The terms policy, procedure, standard, guideline, and baseline should be understood for the exam.

> Policies, Procedures, Standards are **mandatory**, while Guidelines and baselines are **non-mandatory**.

Policies are high level, procedures provide specifics, standards describe technology or process to be followed, guidelines are discretionary recommendations, baselines are uniform ways of meeting a standard. Security governance emphasizes personnel security. Understand importance of security awareness & training, background checks, termination, vendor, consultant, and contractor security, outsourcing and offshoring. The insider / employee is often the greatest threat to security, see Managing Access to Information Resources.

## Security Controls

There are three main types of security controls. Administrative (training, policies, standards, procedures, guidelines, change management, auditing), Technical (network design, IAAA, security devices such as smart cards, biometrics, rights and permissions of users), and Physical (monitoring equipment, physical security devices, environmental controls, security personnel).

| **Controls** | **Administrative** | **Technical** | **Physical** |
| --- | --- | --- | --- |
| **Preventative** | Preemployment drug screening, security policies | Antivirus, Firewall, IDS/IPS | Alarms, Fences, Lighting |
| **Detective** | Mandatory vacations, job rotation | Audit trails / logs, honeypots, | Motion detectors, Security Guards |
| **Corrective** | Backup & Restore Plans | Antivirus / quarantine, rebooting, terminating activity | Fire extinguisher |
| **Recovery** | Procedures | System backups, fault tolerant drives | Backup facility |
| **Deterrent** | Security Awareness, Policies | Warning screens | Locks, Fences, Security Guards |
| **Compensating** | Policies | Additional encryption at various states |

## Risk Management

The main stages of Risk Management include assessment, analysis, mitigation, and monitoring. Risk assessment is the process of identifying and evaluating assets, and identifying threats and vulnerabilities.

> Risk can be quantified as **Risk = Threat \* Vulnerability**. (Sometimes this is multiplied by 'Impact' or severity of the damage in a dollar amount)

There are several methodologies for risk assessment including OCTAVE, FRAP, and NIST 800-30. OCTAVE stands for Operationally Critical Threat, Asset, and Vulnerability Evaluation. It is a self-based assessment carried out directly within the organization. FRAP stands for Facilitated Risk Analysis Process, which is a qualitative assessment that determines which systems warrant further quantitative analysis. NIST 800-30 Risk Management Guide for IT Systems should be more a focus for the exam, and I would recommend memorizing its nine step process outlined below.

| 1 - System Characterization   2 - Threat Identification   3 - Vulnerability Identification | 4 - Control Analysis   5 - Likelihood Determination   6 - Impact Analysis | 7 - Risk Determination   8 - Control Recommendations   9 - Results Documentation |
| --- | --- | --- |

The next step of Risk Management involves a Risk Analysis of the organizations assets. Asset Value (AV) represents the value of an asset that needs to be protected. Risk analysis can be both qualitative and quantitative. Qualitative analysis usually involves a Risk Matrix that categorizes severity on an x axis with likelihood on a y axis, yielding low, medium, high and extreme risk scores. Quantitative analysis on the other hand involves calculations that help determine risk scores based on a number of different variables that can help determine the overall Annual Loss Expectancy (ALE) or cost of a loss due to a risk being exploited. Review the following terms:

- Single Loss Expectancy (SLE) = Asset Value (AV) \* Exposure Factor (EF)
- Annual Loss Expectancy (ALE) = SLE \* Annual Rate of Occurrence (ARO)
- Total Cost of Ownership (TCO) should be > ALE

Exposure factor is the percentage loss of an asset based on an incident. Single Loss Expectancy is the total cost of a single loss, which is calculated by taking the Exposure Factor percentage of the Total Asset value. The Annual Rate of Occurrence is the number of losses over the period of a year and the Annual Loss Expectancy is calculated by multiplying the Single Loss Expectancy by the Annual Rate of Occurrence. The Total Cost of Ownership is a combination of all the up-front costs of mitigating a risk in addition to any maintenance costs associated with it. Therefore TCO should always be higher than the ALE for a positive Return on Investment (ROI).

- **Accept** the risk: Understand consequences and leave unprotected. Not acceptable in all cases (human life)
- **Mitigate** the risk: Lower the risk to an acceptable level via different measures (e.g. anti virus software)
- **Transfer** the risk: Think insurance
- **Avoid** the risk: Avoiding the project or solution altogether to avoid an extreme risk

After risks have been assessed, the organization has a choice to make. Note an organization cannot ignorantly dismiss a risk, even accepting a risk must be considered.

## Attackers

Understand the various types of hackers, bots/botnets, phishers/spear phishers. Understand the difference between insiders and outsiders. See Motivation and Intent of Hackers, Hacking as an Addiction, and Ethical vs Non-Ethical Hackers.
