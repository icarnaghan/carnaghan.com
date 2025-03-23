---
author: "icarnaghan"
title: "Malicious Code Intrusion"
date: 2011-02-14
categories: 
  - "cybersecurity"
tags: 
  - "academic-papers"
  - "csec-610"
---

The last decade has seen a noticeable shift of commercial application development from in-house computer software to the web browser in the form of web applications. Many company web sites today have evolved from small collections of informational pages to a combination of massive database driven applications for sales, marketing, finance, extranets and customer relationship management systems. <!--more-->Through the use of Virtual Private Networks (VPNs) many internal resources can now be accessed through a basic internet connection with the correct software. Intranets, or internal networks used for the purpose of distributing employee resources, have also evolved into more complex web applications providing access to many internal services as well as corporate documentation and policies.

This shift occurred because of a number of reasons including advancements in technology and more efficient development processes for applications running in the web browser. Unfortunately with these advancements also came a number of vulnerabilities, which hackers have been able to exploit causing significant cost to the organizations which fall victim to such attacks. While organizations today still need to be just as vigilant with traditional threats such as viruses and worms, they also have a whole new set of threats to manage. These threats include but are not limited to cross-site scripting attacks, Sequential Query Language (SQL) injections and HTTP attacks on their web applications through the process of submitting malicious code to web servers.

The use of malicious code attacks against web applications is on the rise and is the single most important cybersecurity vulnerability facing I.T. managers today. There are many different types of exploits and vulnerabilities associated with malicious code attacks and this article discusses some of the most common types, which include cross-site scripting and SQL injections. It analyzes them from a organizational perspective and offers advice on how to mitigate the risks involved.

### Understanding the Threat

According to SANS (2009) attacks against websites and web applications constitute more than 60% of total attacks observed on the internet. Any organization that has an open connection to the internet is effectively at risk from many types of attack. In order to understand the vulnerabilities of web applications in general we must first examine the question as to why organizations have shifted traditional client-side applications to the web.

Before the advent of the web, most applications were developed using the traditional client-server model and distributed throughout the organization using portable media such as floppy disks, CD ROMs or even distributed installations through the company network. These applications were built specifically for the operating system they ran on and the client side (or user interface) processes were more complex than many of the lighter forms based web applications we see today. This type of software was more expensive to develop and distribute. Any time an update was released, the system administration team had to ensure all clients were successfully patched or updated by installing the new software on each of the machines. This led to more costly and complicated management of software.

At the end of the 1990s and beginning of the 21st century, many organizations began migration of their old legacy programs to newer web based applications. These newer web-based applications provided a lighter user interface, which could be distributed through a web browser instead of physical installations. The benefits of moving to web applications were an obvious choice for many organizations, which ultimately led to the shift we have seen in recent years. Unfortunately with this shift, we have also seen an increase in application vulnerabilities.

Stern (2004) examines the vulnerabilities of the web application when compared to traditional client-server software. He outlines two major differences in these software models which include heavy client vs. browser and state vs. no state.

#### Heavy Client Vs. Browser

According to his paper, the heavy purpose-built clients used in traditional software development are inherently more difficult to reverse-engineer and therefore more difficult to compromise. When compared to web applications, where the code used to generate can be easily viewed and manipulated through the browser, traditional client-server software is more tightly contained. In addition to this many of the user validations and data input, which was traditionally validated on the client side is often left to the web server to process, opening it up for further vulnerabilities if malicious code is submitted. Some of these vulnerabilities can lead to cross-side scripting (XSS) or SQL Injection attacks.

#### State Vs. No State

Traditional applications provided a direct connection from the user to the application that would provide a continuous session. Once logged in, this session would remain unbroken until the program was closed or the user logged out. In the web application, there is no continuous connection between the user and the application. Unlike a traditional application where the user would physically interact with application on their PC, all communications in web application happens in the form of requests back and forth between the server. These requests are commonly handled using cookies or small text files stored locally on the user’s machine. Cookies can be altered and used to exploit vulnerabilities in a system, which will be discussed in further detail later on. In addition to this, sessions can be intercepted by a hacker and used to gain control of the application or to steal data from the user.

#### Organizational Impact

The move to web applications in many modern business organizations has lead to a significant increase in risk and therefore the responsibility lies with these companies to protect their intellectual assets. Security should be treated as an extremely important investment within the organizations infrastructure because the cost of not having a robust security program is much greater. “Security breaches can cost an organization significantly through a tarnished reputation, lost business and legal fees” (Vacca) 2009.

It is essential for an organization to put in place an effective security program that not only addresses current threats, but also the security needs of tomorrow. At the heart of this security program there must be a comprehensive training program for employees within different divisions of the organization. “Organization members (need to) know what questions to ask and how to find the services they need” (Johnson, E. M., & Goetz, E, 2007).

Software developers and systems administrators should be well versed in the latest trends in information assurance and security threats in order to adequately mitigate any risk to their systems. Tools and resources should be made available where appropriate, for example all developers should have access to software that can assist them in detecting new vulnerabilities with their code.

### Assessing the Vulnerability: Lack of Safeguards Against Malicious Code

The most common vulnerability in web applications stems from a lack of validation or sanitization of data sent to a web application in the form of malicious code. Bergeron (Bergeron, J., Debbabi, M., Desharnais, J. Erhuioui, M., Lavoie, Y., & Tawbi, N., 2001) describe malicious code as “pieces of code that can affect the secrecy, the integrity, the data and control flow, and the functionality of a system.” The two most common attacks come in the form of cross-site scripting and SQL server injections, which take advantage of vulnerabilities in the systems they target. Often these vulnerabilities are present because of poorly written code where little or no thought has been given to systems security. Vulnerabilities can also be caused by poorly configured servers or network firewalls. The process of mitigation should involve collaboration with the software developers and systems administrators or those in charge of allocating and managing information technology resources.

#### Cross-Site Scripting (XSS)

According to Wehrmann (2004), cross-site scripting attacks, often referred to as XSS, are one of the most exploited security vulnerabilities in modern web applications. They work by sending malicious code to the server usually through a URL (Uniform Resource Locator) query string or text box on a web application, which in turn results in an unexpected response from the server. DiLucca (Di Lucca, G.A., Fasolino, A.R., Mastoianni, M., Tramontana, P., 2004) describes cross-site scripting as a susceptibility “that is essentially caused by the failure of the application to check up on user input before returning it to the client's Web browser.” This may cause the user to surrender information unknowingly. XSS attacks can also be caused by cookies or by data already processed and stored in the database. An example of XSS follows.

1. An attacker has located a vulnerability in the web application and creates a URL with malicious code included (usually in the form of Javascript)
2. The new URL is then disguised using a simple HTML anchor text
3. The attacker then uses social networking, SPAM email or other means to distribute the malicious URL
4. The victim then receives this link and once clicked, the malicious code executes that could steal cookies, generate a user session to steal information and in turn steal confidential information.

Cross-site scripting is a very real threat that is increasingly being widely used in numerous attacks against many different organizations. “According to Symantec’s Internet Threat Report, over 17,000 site specific XSS vulnerabilities have been documented in 2007 alone, which constitute over 4 times as many as the traditional vulnerabilities observed in that period” (Saxena & Song, 2008).

#### SQL Injections

SQL injection has been a method of attacking databases through multiple tiers of application infrastructure for many years, MacVittie (2008). SQL or Sequential Query Language is a database language used to interact with large quantities of data, typically stored in tables inside a Relational Database Management System (DBMS). Each command using the SQL language typically generates a result set of data. An example of this follows:

```
select * from accounts
```

The (\*) is effectively used to return (all) columns of data in the ‘accounts’ table. A similar, and more dangerous statement could be issued using the drop command:

```
drop table accounts
```

This command would be used in this example to delete the entire ‘accounts’ table. These examples demonstrate the powerful nature of SQL. In the right hands, it is a very efficient transactional language, however in the wrong hands, could lead to disastrous results through SQL injections. Vacca (2009) describes SQL injection as a “vulnerability that can arise if user input is not properly filtered for string literal escape characters, which can allow an attacker to craft input that is interpreted as embedded SQL statements and thereby manipulate the application running on the database.”

SQL injections are a very common form of attack and over the years developers have worked to protect their applications. Many modern programming languages and frameworks also provide functions and various protections that the developer can use to ensure any information going to the database has been sanitized. Adobe ColdFusion uses the cfqueryparam and cfprocparam tags to strip any data of malicious code before running a query or stored procedure against the database.

### Mitigating the Risk

XSS and SQL injections work because the input sent to the server was not correctly validated or ‘sanitized’ by the web application before submission. In the case of SQL injections, the code is usually sent in the form of a query string formed in an attempt to extract or remove data from the server. Cross scripting attacks usually come in the form of scripting code including Javascript, which is a browser scripting language used to enhance client side interaction with web services. Unfortunately, in the case of XSS, it can be used as an exploit in systems where vulnerabilities are present. Javascript, HTML and other scripting languages use special characters, some of the most common include angle brackets < >, ampersands & and slashes /.

Over the years many developers have become more educated regarding the risks of SQL injection attacks and have put in place defenses accordingly. Unfortunately the same cannot be said regarding the threat of cross-site scripting. According to Wehrmann (2004), most web developers are insufficiently informed about XSS and thus do not take the danger of these potential attacks into account appropriately. As mentioned earlier, it is up to the organization to be aware of the seriousness of malicious code exploits such as XSS and to ensure their developers are appropriately educated about all of the risks. In order to address the vulnerability of successful XSS attacks in a system, a series of steps need to take place which have been broken down into three categories focusing on software developers, systems administrators and users.

#### Coding Defenses: Form Validation, Dynamic Data and Session Management

The developer should protect all points of entry where possible malicious code could be inserted into their application. Protection would involve using special functions to strip out common characters used in code such as those mentioned earlier as well as limiting the size of entry appropriate to each form field. For example, if a user is requested to enter their first name in a form, that field should only process alphabetical characters (and possibly a hyphen) and limit the entry size.

Sanitization or correct encoding of data can be accomplished in most modern computer languages through the use of a basic function. For example, Adobe ColdFusion (a common web development language) uses a function called HtmlEditFormat(), which can be used to prevent processing of any common scripting language characters. Instead it encodes these symbols into friendly html versions. The latest release of Microsoft’s ASP.NET version 4 uses a <%: %> blocks or ‘code-nuggets’ to correctly encode all input fields. Additional restrictions should also be placed in the application to only allow certain types of query string or URL entries to be processed.

XSS succeeds in many circumstances through the manipulation of dynamic output generated by the application. This dynamic output is generated because many web applications provide customized messages to the user based on information they have supplied. Another method of mitigating the risk of successful XSS attacks would involve limiting the use of dynamic responses in the code. By reducing the amount of dynamic output generated by the system, the developer will effectively reduce the risk of successful XSS attacks.

#### Systems Server Defenses: Web Server Configuration and Information Leakage Prevention

In addition to developers, systems administrators should play an important role in mitigating the risks. Part of this involves proper configuration of the company web servers and firewall to only allow the appropriate requested access. For example, if the web application was developed solely using ASP.NET, the web server should not try to process requests for PHP files. A web server is the first point of entry for the request and should be setup to restrict certain types of suspicious data including malformed query strings and altered cookies. Additional care should be taken to effectively manage server responses when a resource is not available.

- All requests for resources on a server that are not present should respond with a page not found message and an appropriate html 404 (not found) code should be sent to the browser.
- All requests for resources on a server that are restricted should respond with a restricted message and an appropriate html 403 (forbidden) header code should be sent to the browser.
- All requests for resources on a server are temporarily unavailable should respond with a not available message an appropriate html 500 (internal server error) header code should be sent to the browser.

All 404, 403 and 500 responses should only contain basic information and should not reveal important server related information that a hacker may be able to use to their benefit. An example of such information would be a badly handled application error revealing the entire stack trace to the hacker including server variables, paths and other related information. This is known as information leakage and is an inherent problem on web servers and applications that have not been correctly configured to handle unavailable system resources.

#### User Defenses: Awareness and Education

While developers and systems administrators can mitigate the risks of malicious code attacks by putting in place the safeguards described above, to a lesser degree increased user education can also play a part in defending against these attacks. Corporations that maintain a large web presence with many customers and clients accessing their sites on a daily basis have an obligation to educate their users of the risks associated with online activities. This has been seen a lot in financial institutions which often provide pamphlets and information on their sites warning customers of the latest phishing scams and other related internet security information. Vogt (Vogt, P., Nentwich, F.,Jovanovic, N.,Kirda, E.,Kruegel, C., & Vigna, G., 2007) discusses a possible solution to XXS attacks from the client side through the use of dynamic data tainting where attacks are prevented by tracking the flow of sensitive information passed through the web browser.

### Web Application Security Testing and Scanning

Traditional software testing focuses on exception or error detection where the user will experience an unexpected halt in the software because of an underlying bug. While this form of testing is still every bit as important today, a newer form of security testing must also take place. Security testing involves testing the software to ensure that it will “continue to function correctly under malicious attack” McGraw (2010). Both types of testing need to take place in a development environment.

A team of well trained developers should be able identify many security holes, however applications are constantly evolving and new security threats are being detected every day. Thankfully scanning software is available to assist with locating security holes. There are various scanning programs, which review the entire codebase of the web application and produce a report highlighting vulnerabilities. HP WebInspect is a well known security testing suite, which provides comprehensive scanning for enterprise level applications. WebInspect examines many different forms of vulnerability taking into account the latest technology trends and security breaches. According to HP (2010), “HP WebInspect easily tackles today’s most complex Web application technologies—including JavaScript, Adobe® Flash, Ajax and SOAP, utilizing HP’s breakthrough testing innovations, for fast and accurate application security tests.” Quite often the problems identified in reports generated from this software will involve collaboration between programmers and systems administrators in order to adequately seal the security hole(s). It is up to the organization to provide tools such as WebInspect to their staff, however, while they should be used to assist developers, they should not be considered a replacement for comprehensive security testing.

### Conclusion

Web application attacks in the form of malicious code injections are a very real threat to any organization with a web presence. XSS, SQL injections and information leakage are among the most common threats associated with malicious code vulnerabilities. Many other vulnerabilities exist which are susceptible to cookie manipulation, session hijacking and other http server attacks. As systems become more advanced so too do the methods hackers use to infiltrate them. It is therefore up to the organization to devise and implement a comprehensive security program that encompasses all operations of the company.

Server and system administrators, which have traditionally been in a separate division from that of the developers all need to work together to effectively combat the ever growing list of threats to their systems. Quite often a developer may be very good at writing software, but lack the necessary server knowledge to effectively secure their applications. Developers should be carrying out security testing on all code they release by identifying vulnerabilities and using tools such as HP WebInspect to help identify other problems which they may have missed. Employees need to be educated in the threats of cybersecurity and effectively communicate those risks to their customers and clients.

According to the Web Application Security Consortium (2010) statistics from January 2010 show that XSS, information leakage and SQL injection attacks are among the highest number of incidents reported. Organizations must be pro-active in all security matters in order to mitigate the risks involved. While the costs of implementing and maintaining a comprehensive security program are high, the risks in not doing so could lead to greater costs and loss of reputation.

References:

1. Bergeron, J., Debbabi, M., Desharnais, J. Erhuioui, M., Lavoie, Y., & Tawbi, N. (2001) Static detection of melicious code in executed programs. Int. J of Req. Eng. Retrieved from http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.102.6845&rep=rep1&type=pdf
2. Johnson, E. M., & Goetz, E (2007). Embedding Information Security into the Organization. IEEE Security and Privacy, pp. 16-24, May/June, 2007
3. Di Lucca, G.A., Fasolino, A.R., Mastoianni, M., Tramontana, P. (2004). Identifying cross site scripting vulnerabilities in Web applications. Web Site Evolution, 2004. WSE 2004. Proceedings. Sixth IEEE International Workshop. Retrieved from http://ieeexplore.ieee.org.ezproxy.umuc.edu/xpls/abs\_all.jsp?arnumber=1410997&tag=1
4. HP. (2010). HP WebInspect Datasheet. Retrieved from https://h10078.www1.hp.com/cda/hpms/display/main/hpms\_content.jsp?zn=bto&cp=1-11-201-200^9570\_4000\_100\_\_
5. MacVitti, L. (2008). SQL Injection Evasion Detection. ISSA Journal. Retrieved from http://www.issa.org/Library/Journals/2008/February/MacVittie-SQL%20Injection%20Evasion%20Detection.pdf
6. McGraw, G. (2004). Software Security. Security and Privacy, IEEE, pp. 80-83, March/April, 2004
7. SANS (2009). The Top Cyber Security Risks. Computer Security Training, Network Research & Resources. Retrieved from http://www.sans.org/top-cyber-security-risks/
8. Saxena, P., Song, D. (2008). Document structure integrity: A robust basis for cross-site scripting defense. In Proceedings of NDSS'08, 2008.
9. Stern A., Web Application Vulnerabilities. The ISSA Journal. Retrieved from http://www.f5.com/f5/news/articles/article030905.html, downloaded 2005-04-06 11:45
10. Vacca, J. (2009). Computer and Information Security Handbook. Burlington, MA: Morgan Kaufmann Publications.
11. Vogt, P., Nentwich, F.,Jovanovic, N.,Kirda, E.,Kruegel, C., & Vigna, G. (2007). Cross-Site Scripting Prevention with Dynamic Data Tainting and Static Analysis. In Proceeding of the Network and Distributed System Security Symposium (NDSS’07), February 2007.
12. The Web Application Security Consortium. (2010). Web Application Security Statistics. Retrieved from http://projects.webappsec.org/w/page/13246989/Web-Application-Security-Statistics
13. Wehrmann, C. (2004). Cross Site Scripting. Seminar: Security in Communication Systems SS 2004. Retrieved from http://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.141.7589&rep=rep1&type=pdf
