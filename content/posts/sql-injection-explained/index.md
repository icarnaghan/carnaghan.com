---
author: "icarnaghan"
title: "SQL Injection Explained"
date: 2015-10-29
categories: 
  - "coding"
  - "cybersecurity"
tags: 
  - "csec-630"
---

SQL injection has been a method of attacking databases through multiple tiers of application infrastructure for many years, MacVittie (2008).  SQL or Sequential Query Language is a database language used to interact with large quantities of data, typically stored in tables inside a Relational Database Management System (DBMS).  Each command using the SQL language typically generates a result set of data.  An example of this follows:

```
select * from accounts
```

The (\*) is effectively used to return (all) columns of data in the ‘accounts’ table.  A similar, and more dangerous statement could be issued using the drop command:

```
drop table accounts
```

This command would be used in this example to delete the entire ‘accounts’ table.  These examples demonstrate the powerful nature of SQL.  In the right hands, it is a very efficient transactional language, however in the wrong hands, could lead to disastrous results through SQL injections.  Vacca (2009) describes SQL injection as a “vulnerability that can arise if user input is not properly filtered for string literal escape characters, which can allow an attacker to craft input that is interpreted as embedded SQL statements and thereby manipulate the application running on the database.”

SQL injections are a very common form of attack and over the years developers have worked to protect their applications.  They can be addressed or mitigated by ensuring web applications sanitize all inputs that could potentially be sent for a query result. Sanitization is the process of converting literal escape characters or command key words into a safe format or string that would never be executed on the database. Many modern programming languages and frameworks provide functions and various protections that the developer can use to ensure any information going to the database has been sanitized.  Adobe ColdFusion for example uses the cfqueryparam and cfprocparam tags to strip any data of malicious code before running a query or stored procedure against the database. Newer versions of the .NET framework and ASP.NET MVC provide input field sanitization by default for all form and database controls.

References:

MacVitti, L. (2008). SQL Injection Evasion Detection. ISSA Journal. Retrieved from http://www.issa.org/Library/Journals/2008/February/MacVittie-SQL%20Injection%20Evasion%20Detection.pdf

Vacca, J. (2009). Computer and Information Security Handbook. Burlington, MA: Morgan Kaufmann Publications.
