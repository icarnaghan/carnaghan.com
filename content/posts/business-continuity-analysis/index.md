---
author: "icarnaghan"
title: "Business Continuity Analysis"
date: 2017-11-28
categories: 
  - "cybersecurity"
tags: 
  - "academic-papers"
  - "csec-650"
---

The purpose of business continuity planning is to ensure continued operations of an organization in the event of a catastrophic event, whether this may be a natural disaster or something more sinister. In recent years, we have seen the increase of cyber-attacks and breaches to the point that they have become common news worldwide. As systems have grown in complexity and capacity to store large amounts of data, so too has the appeal of targeting such systems by cyber criminals. In order to meet these challenges head on, business organizations must adapt and implement a comprehensive business continuity plan. Cerullo and Cerullo (2004) describe a business continuity plan as dynamic and evolving as the business environment changes and its dependency on advanced technology changes. They go on to describe three interdependent objectives which include identification of major risks, development of a plan to mitigate or reduce impact of risks, and testing and training. While there is no single recipe to the ideal continuity plan, stakeholders across the organization must play a role in building out a framework for business continuity management that can be used to mitigate major risks while maintaining ‘business as usual’ in the event of a disaster.

The sections that follow include an overview of planning and carrying out a Business Impact Analysis (BIA), which identifies critical functions of any given organization. Next recovery options are addressed focusing on systems and data retrieval of the impacted infrastructure. Finally, testing requirements are covered in depth including a proposed 24-month cycle business continuity testing plan. Pivotal to all of these processes is a thorough understanding of risk associated to the business, its assets, and the overall infrastructure which it lives.

## Introduction

Businesses are facing increasing risks and challenges more than ever before due to the complexities of the systems they maintain on a day to day basis. Attacks against web sites and web applications are on the rise and continue to remain at the forefront of organizational security policies. Business continuity has traditionally been focused on catastrophic events such as natural disasters, which have required plans for migrating physical equipment and personnel to alternative sites of operation. In recent years cyber-attacks have become common place and therefore impact continuity planning. At the center of continuity planning lies careful assessment of the risks involved, which essentially equate to any chance that a system or systems within the organization will either come under attack or destruction due to both deliberate and non-deliberate actions. From a strictly digital perspective, continuity focuses on simply being able to ‘continue to function correctly under malicious attack’ McGraw (2010).

In addition to maintaining business continuity for the survival and well-being of an organization, in recent years it has become a mandatory requirement enforceable by external parties. According to Balaouras (2009), business organizations must provide proof of business continuity readiness to regulatory auditors, first responders, strategic partners, and customers. Balaouras (2009) also affirms that there are three critical phases within business continuity planning, which include Business Impact Analysis (BIA), Risk Assessment (RA), and plan documentation. In recent years due to regulatory shifts and the impact of cyber-attacks on both local and international businesses, organizations have been shown to pour more resources and expenditure into solid business continuity planning processes. The policies and documentation that are resultant from properly thought out business continuity processes are living documents that are updated on a regular basis. As risks change over time, so too do will these processes and policies. Planning, recovery, and testing are three essential phases that encapsulate the above processes and provide a roadmap for the organization’s business continuity planning. Each of these are explored in the sections that follow and provide recommendations on how best to implement policies and procedures in line with continuity and risk tolerance.

## Planning

At the heart of any business continuity planning should live a solid security plan and set of disaster recovery precautions. These should be updated and revised periodically to address ever changing challenges faced by the organization. In addition to having an up-to-date plan, an approach to mitigating risks associated with the information systems of the organization should be implemented. A risk analysis should be carried out involving a holistic approach and careful investigation of information systems and the overall environment. The purpose of such an analysis is to evaluate all endpoints that could potentially fail in a disaster or cyber-attack. Pfleeger and Fleeger (2007). The analysis should describe the current state of an organization’s security approaches and examine areas of the company’s infrastructure as well as external factors. At the core of any comprehensive security policy, should be a focus on confidentiality, availability and integrity of information assets including Personally Identifiable Information (PII) or other sensitive data.

### Disaster Recovery vs Business Continuity

Before thinking about planning, it is essential to understand what we are planning for. The term ‘Disaster Recovery’ has been used by business organizations for many years and often can be confused with business continuity. In reality, while both of these terms share a common set of principles, there are differences that organizations should be aware of in order to not miss any essential factors in their planning processes. Potts (2013) documents the confusion and often overlapped use of these terms in his article comparing disaster recovery with business continuity. The underlying difference between the two lies in the fact that disaster recovery is a subset, or small part of overall business continuity. Traditionally this has meant that disaster recovery has a greater focus on managing backup systems to preserve data in the event of a catastrophic. Disaster recovery is concerned with managing a plan to preserve important business assets and should be a part of the organization’s security plan. Business continuity in contrast to this focusses on more than just backup and recovery of assets. It is in essence a broader picture including operations, management of staff and facilities, migration to new premises of operations, and limiting or eliminating any down time associated with the transition. Disaster recovery policies and procedures should usually be in place prior to beginning a business impact analysis and focus on business continuity.

### Business Impact Analysis (BIA)

A Business Impact Analysis (BIA) aims to identify critical business functions and use current-state knowledge to rank them accordingly based on an overall impact of a disruption to them. Warrier (2017). It essentially provides an important starting point for defining and building on company disaster recovery strategies, which are in turn used to respond to a catastrophe or any form of disruption to critical systems. Warrier (2017) points out that there should be two main goals of any successful BIA; prioritization, and sequencing. Prioritization focuses on analyzing all existing business functions using existing organizational knowledge in order to rank them. Priorities should take into account recovery time, dependencies on other systems and their recovery time, and overall financial impact. Other factors that may not be as easy to calculate, but should be ranked accordingly include employee morale, company reputation, customer confidence, and public relations. Sequencing on the other hand is concerned with restoration of business operations and the sequence in which they can be resumed.

### Risk Assessment

While the BIA serves an essential role in planning, a thorough risk assessment should follow to ensure that the organization has taken into account all threats associated with disruption of services. Tjoa, Jakoubi, and Quirchmayr (2008) describes the process of risk assessment and outlined five main steps:

1. Identification of all threats to selected processes
2. Estimation of the impact of each threat and potential occurrence rate
3. Determination of the probability / likelihood of each threat
4. Calculating the risk out of the previous activities
5. Selection of a risk strategy for each threat (acceptance, transfer, avoidance, reduction)

Finally, it is important throughout any planning to document and maintain mitigation strategies, including preventative controls. Continuous monitoring plans should also be put in place such as the Department of Homeland Security’s Continuous Diagnostics and Mitigation (CDM) framework. Department of Homeland Security (n.d.). Such processes would enable organizations to identify cybersecurity threats on an ongoing basis and continually evolve their own security strategy to defend against attacks. Such plans should include documented incidence response strategies identifying key personnel and actions taken in the event of a disruption.

## Recovery Options

Traditionally recovery options for business organizations have been grouped into two main areas, backup recovery and alternative site setup. In recent years and with advent of cloud computing, the complexities of both of these options has been reduced, as has the cost. Depending on whether or not an organization has adopted cloud computing such as Amazon Web Services (AWS), or they maintain their own physical infrastructure, will have an impact on their recovery options strategy. Regardless of the nature of the infrastructure, recovery options still need to be carefully determined. Any recovery strategy should take into account recovery time objective (RTO) as well as recovery point objective (RPO). Robinson, Vamvadelis, and Narin (2014) provide a concise overview of each listed below.

- **Recovery Time Objective (RTO)** considers the amount of time acceptable to restore normal business. An example of this could entail a disaster that occurred at 12:00 PM with an RTO of eight hours. This would result in a process to restore business operations by 8:00 PM.
- **Recovery Point Objective (RPO)** is concerned with the acceptable amount of data loss measured in time. An example of this could entail a disaster that occurred at 12:00 PM with an RTP of 1 hour. This would result in a process to recover all data that was in the system before 11:00 AM.

### Backup recovery

A strategy solely concerned with backup recovery is one that takes into account all systems within the infrastructure and the backup processes in place. Considerations should be made based on the BIA in terms of system importance and cost. In the event of a disaster, a backup restore process would be responsible for capturing all data, code, and server images. Without taking into consideration setup of an alternative site, a realistic restore period of time would need to be established. This traditionally speaks to disaster recovery in terms of ranking the highest importance with data recovery but not taking into account continuity.

### Alternative site setup

By considering an alternative site to run operations in the event of a disruption or catastrophic event, the organization would consider the importance of ensuring all systems were back online within a specified period of time. For a physical space in the traditional sense of the organization managing its own hardware, the costs of maintaining a fallback location could be costly. In the cloud, this is simplified greatly through the use of availability zones (or data centers) across geographic regions. Robinson, Vamvadelis and Narin (2014) describe three different scenarios for recovery using virtualized cloud technology, which could also translate into physical location setup; pilot light, warm standby, and multi-site. Each of these are summarized below.

Pilot light is analogous to running a pilot light on a gas stove. It is the process of setting up a bare-bones infrastructure in an alternative location that contains the most critical core elements of an organizations systems. The systems are not actively running, but are ready to be provisioned in the event of a disruption at the main location. The idea behind this strategy is to allow for a starting point that could potentially be ‘quickly lit’ to serve business continuity across the organization. Warm standby in contrast refers to a scaled down version of a fully functioning environment that is always running. This approach extends the pilot light elements and preparation and further reduces the overall recovery time because some of the services needed for the infrastructure are always running. The third approach to an alternative site setup is setting up a multi-site infrastructure. This would involve the process of setting up the exact same infrastructure in two different locations. If the primary location should fail due to an unplanned disruption, processes would be in place to roll over to the backup location.

The table below summarizes the cost and recovery time associated with each of these strategies in a typical cloud infrastructure such as Amazon Web Services (AWS). In a physical environment, the times listed would vary depending on the geographical location of the backup site and the time allotted to for support personnel to relocate (if neededs and provision the necessary additional hardware and resources.

**Table 1: Alternative Site Strategies**

|   | **Pilot Light** | **Warm Standby** | **Multi-Site** |
| --- | --- | --- | --- |
| **Cost** | Low | Low-Medium | Very High |
| **Recovery Time** | 4 Hours | 2 Hours | Few Seconds |

Depending on the organization’s risk tolerance, choices will need to be made in order to determine the best strategy. That decision will depend on the amount of knowledge security personnel can convey to management regarding the importance of protecting the organization’s business assets as well as continuity versus budget constraints.

## Recommended Testing Requirements

Once an organization has completed the planning processes and determined their strategy for recovery, the next step should include a review of the overall action plan that needs to be put in place. The action plan should provide opportunity to define actions that need to be executed in the event of a disruption or disaster. In order for an action plan to be useful, it is necessary to consider the teams of staff that may be involved in each step.

The proposed action plan below includes three main groups responsible for various activities. The Business Continuity (BC) team would be responsible for all disaster management activities from assessing initial damage through to returning to normal operations. Facilities would involve all building and location facilities personnel, responsible for the physical environment and staff safety. I.T. Operations would manage all activities involved with analysis and recovery of servers and other technology assets. A typical action plan could include the following steps, which may vary depending on the organization.

**Table 2: Action Plan**

| **Task** | **Team** |
| --- | --- |
| **Conduct Assessment of Damage** | BC Staff, Facilities, IT Operations |
| **Identify critical applications** | BC Staff, Operations |
| **Communicate status and projected down time** | BC Staff |
| **Coordinate resources needed for alternative location** | BC Staff |
| **Retrieve backups needed for continuity** | I.T. Operations |
| **Provision backup equipment at alternative location** | I.T. Operations |
| **Communicate new procedures** | BC Staff |
| **Procure and provision replacement equipment** | I.T. Operations |
| **Communicate return to normal operations** | BC Staff |

While the action plan provides a step-by-step set of processes for an organization to return to normal operations, it is a high-level overview and the activities that support each step must be tested thoroughly. The above table also doesn’t take into consideration other communications that should take place including but not limited to alerting customers or clients to possible disruptions to service. The section that follows explores a proposed testing plan that could be used to ensure the organization is ready to successfully carry out any processes needed for successful business continuity.

## Business Continuity Testing

In order to create a valid testing plan, we must first consider what should be tested as well as how each test should be conducted.  Sharrieff (2017) recommends considerations that should be followed when conducting testing of a business continuity plan. These include conducting a plan review on a regular basis, conducting disaster role-playing (table-top) sessions, performing a simulation of a possible disaster scenarios, accommodating any work stoppages, and communicating the importance of testing throughout the workplace community. Details concerning testing around the organizations action plan for continuity and recovery are essential. Two main types of tests are often used in contingency testing plans along with typical review. These include tabletop testing (as mentioned in the steps above) and technical testing. Table top testing is an informal brainstorming session used to encourage participation from business leaders and other key employees. Ezecastle (2015). The idea behind this type of testing is that a lead consultant within the BC staff would lead a discussion within a group session that would cover all details and tasks needed to be completed in order to carry out the action plan. Technical testing in contrast is concerned with communication processes, data storage and recovery in order to viably function at an alternative site to perform business functions within designated requirements. HIPAA (n.d.). These types of tests can involve full-blown backup and recovery processes to ensure the systems in place can handle the requirements outlined in the plan.

### Proposed 24-month cycle business contingency testing plan

Once the organization has made decisions based on the Business Impact Analysis and chosen an appropriate strategy for their recovery options, the next step is to formulate an ongoing testing plan. The plan that follows takes into consideration the action steps needed in order to recover from a disruption as well as regular review and testing to confirm its validity and effectiveness in real life scenarios. The plan breaks down testing activities by the teams involved and includes a high-level overview of the tests carried out, actions taken, and predicted outcomes.

**Business Continuity Staff**

- Test: Table Top, Review (Quarterly)
- Actions: Evaluate damage, ensure personnel safety, coordinate and attend meetings
- Outcomes: Make decisions, coordinate activities, communication to senior management, users, suppliers, customers, employees, and the press.

**Facilities**

- Test: Table Top, Review (Quarterly)
- Actions: Assess damage, coordinate and attend meetings, prepare migration to alternative location
- Outcomes: Salvage operations, manage and coordinate repairs, manage and coordinate moving of staff and resources

**I.T. Operations**

- Test: Technical, Table Top (Quarterly with test infrastructure migration every 6 months)
- Actions: Coordinate and attend team meetings, preparation work to move resources to alternative location
- Outcomes: Dry run migration and operation at alternative location with provisioning of virtual or physical equipment and resources.

The above tests would be measured against baseline requirements including proposed response times and the required actions that should be accomplished with the specified window of time. In addition to the team activities outlined above, the organization should develop several scenarios to base the tests on. Examples of these scenarios could better serve role playing activities in table-top tests and would drive decisions made in technical activities involving backup recovery and migration efforts. Different scenarios could involve disruptions resulting in minor damage, major damage, or catastrophic damage.

Costs associated with the tests would also have to be considered, including labor, equipment and alternative location specific expenses. Budgeting for technical tests should include costs for temporarily increased facilities and resources (whether cloud based or physical). In addition to the proposed schedule of testing, a comprehensive yearly review should occur that brings all teams together to discuss any potential improvements or gaps revealed that should be mitigated in the plan.

## Conclusion

This article has highlighted an overall approach to comprehensive continuity planning with a business organization. Every organization is different and will no doubt have distinctive requirements depending on the nature of their business, size, customers, and the type of services they provide. Regardless of the type of organization however, it should be clear that a thorough plan should be in place to enable proper business continuity planning. It has become more important in recent year as the frequency of cyber-attacks has continued to grow and the number of threats to everyday businesses are evolving and becoming more advanced.

For any business to be successful in continuity planning, they will need to account for the costs associated with planning, testing and continually updating policies to better protect their infrastructure, assets, and employees. In larger organizations, these costs will be greater and it will be the responsibility of cyber security experts within the business to make the case for such expenditures. In the end however, the organizations who are going to be better equipped to face disasters, whether natural forming or cyber-attacks, will be those who have a comprehensive plan in place that is continually vetted and enhanced over time.

## References

Balaouras, S. (2009). Businesses take BC planning more seriously. (2009). _For Security & Risk Professionals_.

Cerullo, V., & Cerullo, M. J. (2004). Business continuity planning: a comprehensive approach. _Information Systems Management, 21_(3), 70-78.

Department of Homeland Security. (n.d.) Continuous Diagnostics and Mitigation (CDM). Retrieved from: https://www.dhs.gov/cdm

Execastle. (2015). Business Continuity Planning: The Importance of Table Top Exercises. Retrieved from: https://www.eci.com/blog/213-business-continuity-planning-the-importance-of-table-top-exercises.html

HIPAA (n.d.). Disaster Recovery Policy. Retrieved from: https://github.com/clinical-meteor/hipaa-policies/blob/master/policies/disaster\_recovery\_policy.md

Pfleeger, C., P., & Fleeger, S., L. (2007). _Security in Computing Fourth Edition_. Upper Saddle River: NJ. Prentice Hall.

Robinson, G., Vamvadelis, I., & Narin, A. (2014). Using Amazon web services for disaster recovery. Retrieved from: https://www.turningtechnologies.com/pdf/content/AWS-Disaster-Recovery.pdf

Tjoa, S., Jakoubi, S., & Quirchmayr, G. (2008, March). Enhancing business impact analysis and risk assessment applying a risk-aware business process modeling and simulation methodology. In _Availability, Reliability and Security, 2008. ARES 08. Third International Conference on (pp. 179-186)_. IEEE.

Warrier, R. (2017). The Two Goals of a Business Impact Analysis (BIA). eBRP. Retrieved from: https://www.ebrp.net/the-two-goals-of-a-business-impact-analysis-bia/
