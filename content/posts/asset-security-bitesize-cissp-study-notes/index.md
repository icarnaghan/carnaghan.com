---
author: "icarnaghan"
title: "Asset Security – Bitesize CISSP Study Notes"
date: 2019-09-12
categories: 
  - "cybersecurity"
---

Asset Security is the second domain of the CISSP. This domain focuses heavily on classification of data and labels used, various roles within an organization, data security controls and frameworks, baselining and hardening, and the various states of data. In addition to this data remanence and destruction are also covered and should be understood for the exam, especially understanding the difference between traditional magnetic storage vs newer solid state devices.

## Classification of Data

The purpose of data classification is to determine the type of security controls needed for different categories of data. The process of classification involves determining the value or cost associated with the data, classifying based on cost, and placing controls on the data (cost -> classify -> control). Consider cost as the amount of money an organization could potentially lose of a breach were to occur (e.g. legislation, reputation, etc.). Various labels of classification are applied both in government and non-government based on various classes in order of severity. These are shown in the table below.

| Class | Government | Non-Government | Outcome of Breach |
| --- | --- | --- | --- |
| 3 | Top Secret | Confidential / Proprietary | Exceptionally Grave Damage |
| 2 | Secret | Private | Serious Damage |
| 1 | Confidential | Sensitive | Damage |
| 0 | Unclassified | Public | No Damage |

In a typical organization, the data owner is responsible for classifying data and the data custodian is responsible for maintaining it. More on roles below. Finally understand the difference between sensitivity (amount of damage caused) and criticality (time sensitivity to return to operations).

## Owners of Data

There are various stakeholders within an organization that should be considered when dealing within information assets. These include senior and executive management comprised of the CEO, CFO, CIO, and ISO.

> The ISO (Information Security Officer) is responsible for communicating risks, recommending best practices, establishing security measurements, ensuring compliance, and spreading awareness of emerging threats to senior and executive management.

In Steering committees are responsible for defining risks, objectives and approaches. Auditors are another key stakeholder, however usually this is an external entity from the organization performing security audits of the company owned resources. Understand the roles and responsibilities of the various stakeholders, outlined below.

| Owner | Responsibilities |
| --- | --- |
| Business Owners | Senior or Executive management responsible for creating the security program and ensuring it is staffed and funded. |
| Data Owners | Determine sensitivity labels, backup cadence, and other management duties associated with data. |
| System Owners | Responsible for managing the computers or systems that house data, including updating, patching, system hardening, etc. |
| Data Custodian | Executes or carries out hands-on tasks under direction of the data and system owners. |
| Users | Responsible for complying with mandatory policies, procedures, and standards. |

In addition to the list above, data controllers and data processors should be considered. Data controllers are responsible for the creation of and management of data of a sensitive nature. Data processors are individuals or teams that manage data on behalf of the data controllers (e.g. an outsourced payroll contractor). Also another important note - organizations should have separate network administrators and security administrators wherever possible (think separation of duties).

## Data State and Remanence

Data can exist in various states within a computer system or network. The most common way of looking at this is by breaking down **data at rest, data in transit, and data in process**. Data at rest should be encrypted. Understand that OS specific encryption such as EFS on Windows, may not provide the best security if a drive is removed and placed in a different system.

> TPM (Trusted Platform Module) enables whole drive encryption and stores a key in hardware to protect data on stolen drives.

Products such as Bitlocker and PGP provide this level of encryption. Data in process needs to remain unencrypted for use, therefore other security mechanisms must be considered such as good security policies, screen protectors, and other physical security measures. Data in transit should be protected by IPSec or TLS/SSL. Data can be stored within different forms of memory throughout its different states. Understand the different types of memory outlined in the table below.

| Memory | Description |
| --- | --- |
| RAM (Random Access Memory) | RAM is primarily used for running programs and is volatile (i.e. will be erased on power off). |
| ROM (Read Only Memory) | ROM is nonvolatile and typically used in computer chips such as the BIOS that stores persisted settings. |
| Dynamic RAM (DRAM) | DRAM stores bits in capacitors that need to be refreshed in order to maintain integrity. Typically used as main memory. |
| Static RAM (SRAM) | SRAM is faster than DRAM and more expensive, typically used as cache. Uses latches (flip-flops) to store bits and does not require refreshing. |
| Programmable ROM (PROM), Erasable Programmable EPROM, Electronic EPROM (EEPROM) | PROM can be written once. EPROM can be erased and programmed by flashing UV light over a small window on the chip. EEPROM can be 'flashed' with software. |

Remanence is a term used to describe 'residual' representation of data left behind after attempts have been made to remove it from magnetic media such as traditional hard disks. For the purpose of the CISSP, remanence can also refer to newer storage mediums such as Solid State Devices (SSDs). There are four main ways to destroy data:

- **Overwriting**: Deleting files or formatting a drive results in remanence (data left behind). Reformatting simply rewrites the old File Allocation Table (FAT), however data remains. Overwriting every file or every block is more secure through processes of electronic shredding or wiping.
- **Degaussing**: The process of exposing magnetic media to a strong magnetic field in order to destroy the data. Note this does not work on newer SSD or non-magnetic medium.
- **Destruction**: Physically destroying the device (hard drives, servers, etc.) through means of pulverization, incineration, shredding, or submersing in acid. Destroying devices is more secure than overwriting or degaussing.
- **Shredding**: Making unrecoverable and data or information that has been stored on physical medium (hard copies printed on paper).

## Data Security Controls - Standards and Control Frameworks

Listed below are the main frameworks used in organizations. Know ISO27000 well for the exam if you have to focus on one. Below PCI-DSS was developed by the Credit Card industry, OCTAVE is self-directed risk management.

| PCI-DSS | OCTAVE |
| --- | --- |
| Build and maintain secure network and systems   Protect cardholder data   Maintain vulnerability management program   Implement strong access control measures   Regularly monitor and test networks   Maintain an information security policy | Phase 1: identifies staff knowledge, assets, and threats   Phase 2: identifies vulnerabilities and evaluates safeguards   Phase 3: conducts risk analysis and develops risk mitigation strategy |

| International Common Criteria | ISO17799 / 27000 |
| --- | --- |
| EAL1: Functionally tested   EAL2: Operationally tested   EAL3: Methodically tested and checked   EAL4: Methodically designed, tested, and reviewed   EAL6: Semi-formally designed and tested   EAL7: Semi-formally verified, designed, and tested   EAL8: Formally verified, designed, and tested | Policy   Organization of information security   Asset management   Human resource security   Physical and environmental security   Communications and operations management   Access control   Information systems acquisition, development, and maintenance   Information security incident management   Business continuity management- Plan and organize   Compliance |

Understand that COBIT (Control Objectives for Information and related Technology) is about goals for IT and COSO (Committee of Sponsoring Organizations) focuses on goals for the organization as a whole. Understand that ITIL is all about IT Service Management (COBIT & COSO Goals Oriented, ITIL is how to implement).

COBIT

- Plan and organize
- Acquire and implement
- Deliver and support
- Monitor and evaluate

In addition to the frameworks above, know about the Plan Do Check Act (PDCA) model, developed by Denning:

- Plan: Establish Information Security Management System (ISMS)
- Do: Implement and Operate ISMS
- Check: Monitor and Review ISMS
- Act: Maintain and Improve ISMS

Finally for this section, understand that preferable security model is top-down, directed from senior management (who are ultimately responsible). Bottom up approach is not preferable,
