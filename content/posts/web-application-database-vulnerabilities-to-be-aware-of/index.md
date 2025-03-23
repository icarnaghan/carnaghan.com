---
author: "icarnaghan"
title: "Web Application Database Vulnerabilities to be Aware of"
date: 2015-11-01
categories: 
  - "coding"
  - "cybersecurity"
tags: 
  - "csec-630"
---

The use of malicious code attacks against web applications and more specifically, web enabled databases, is on the rise and continues to be a greater threat as systems become more complicated and reliant on third party libraries and frameworks.  There are many different types of exploits and vulnerabilities associated with malicious code attacks which can potentially threaten the very databases that power such applications. Several areas of vulnerabilities are discussed below.

## SQL Injection

One of the most common vulnerabilities is the SQL injection attack, which is commonly mitigated in modern application development practices. SQL injections work because the input sent to the server was not correctly validated or ‘sanitized’ by the web application before submission.  The code is usually sent in the form of a query string formed in an attempt to extract or remove data from the server. Over the years many developers have become more educated regarding the risks of SQL injection attacks and have put in place defenses accordingly. In addition to this most modern web application development frameworks have built in sanitizers to mitigate the risk of SQL in code.

## Database Connection Strings

In recent years, vulnerabilities with database or SQL connection strings has been on the rise. A connection string is essentially a group of access instructions and credentials, often including a username and password to the database along with server specific data. In recent years Connection String Parameter Pollution attacks (CSPP) have been increasing whereby hackers exploit vulnerabilities associated with connection strings in web applications. Unlike the more common SQL injection vulnerabilities where flaws exist in the way database queries are crafted, this type of attack targets the way applications connect to the database itself. Alonso et al (2010). If carried out successfully CSPP can be used to steal user credentials and hijack web credentials. It is especially high risk because it can be carried out with minimal technical skills and the impact it has is critical. Maurice (2010). In addition to CSPP, if connection strings are carelessly published in areas of the server that an attacker might have access to, there is a potential for a full database compromise.

## Application Framework Vulnerabilities

Another major vulnerability that affect web enabled databases is common knowledge of application framework exploits. Whenever new vulnerabilities are discovered in commonly used content management systems such as Drupal and WordPress, published security alerts are sent out. If the applications are not patched in a reasonable amount of time, exploits can be taken advantage of by attackers. Take for example the Drupalgeddon exploits discovered in late 2014 and documented at Drupal.org. These back door exploits impacted the Drupal community and users of the popular CMS. Within a very short amount of time several patches were released, however recommendations were made to restore from earlier backups if they were not applied within a matter of hours. Similarly other popular platforms undergo security updates periodically that if not patched in a timely manner can lead to compromises.
