---
author: "icarnaghan"
title: "Security Issues to be Addressed by ISPs"
date: 2000-05-15
categories: 
  - "business"
  - "cybersecurity"
  - "hosting"
---

> The Internet has become a vast marketplace for global goods and services. For e-commerce to prosper, you have to feel safe about transmitting credit card and other financial information over the Internet. Because information traveling over the network actually passes through many computers along the way, the opportunity exists for someone to steal confidential information. Hackers also break into computers to steal data. No one really knows how often this actually happens.
> 
> Michael Lerner Productions (2000) Protect Yourself: Secure Transactions  
> http://www.learnthenet.com/english/html/07secur.htm (April 14th, 2000)

## Business Security Needs

Security has been an ongoing issue with regard to the Internet ever since its birth. It has become more of a growing concern however in recent years with the increasing popularity of online shopping and e-commerce in general. The question of how secure the Internet really is has become a very important area of investigation. But what exactly has all this to do with the common Internet Service Provider?  

> A growing number of companies are placing some or all of their Internet-commerce support needs into the hands of business service ISPs or one-stop, no-hassle Web hosting service centers.
> 
> Radcliff, D (1998) Is your ISP secure?  
> http://www.idg.net/crd\_security\_7784.html (April 14th, 2000)

Unfortunately server systems used within common business ISPs have become very tempting targets for hackers and people wishing to violate the system. Once a system has been violated the harm that can be caused depends highly on the amount of sensitive information stored within the server.

In order to increase the overall security of a host server used within an ISP, a ‘Firewall’ can be implemented. A firewall can significantly improve the overall security of a server, while at the same time allowing authorized access to necessary Internet services.

![](images/figure40-1024x331.png)

> ‘A firewall is an approach to security; it helps implement a larger security policy that defines the services and access to be permitted, and it is an implementation of that policy in terms of a network configuration, one or more host systems and routers, and other security measures such as advanced authentication in place of static passwords. The main purpose of a firewall system is to control access to or from a protected network or server. It implements a network access policy by forcing connections to pass through the firewall, where they can be examined and evaluated.’
> 
> Wack, J (1995) The Firewall Concept  
> http://csrc.ncsl.nist.gov/nistpubs/800-10/node31.html#SECTION00510000000000000000  
> (April 19th 2000)

In order for the common ISP to protect their servers from either data corruption or more importantly, unauthorised access, a firewall becomes a necessity that must be maintained at all times. Many smaller ISPs have spent very little money in securing their servers which has ultimately led breaches of security. The main problem area for these smaller Providers lies in the fact that they do not have large resources to spend on security and hence led to less secure systems. The answer to this problem lies within outsourcing to larger network providers.

‘ISPs are vague about attacks they have experienced, saying they are unaware of actual intrusions into their networks.’

Breach of security is a major threat in any organisation, so it is vital that adequate measures have been put in place to prevent this as much as possible. However as any organisation involved with Information Technology already knows, no system is 100% secure! Many smaller ISPs as well as the larger industry players have needed to become more aware of the threats and dangers to their customers’ information. Many organisations believe that all ISPs have adequate security, but this has not always been the case, and more ISPs are realising that security has become a more important and costly but necessary area to enhance.

‘Large, backbone ISPs that have security departments are on top of their security, but it trails off when ISPs get smaller and don't have dedicated security departments.’

Obviously the larger the ISP the larger resources are available to increase the security of their systems. As mentioned earlier, a lot of smaller ISPs are moving towards becoming VISPs offering connections to their customers through outsourcing the physical connections.

Virtual Hosting is becoming more popular with these smaller companies meaning that they no longer have to maintain the actual server storing their customers web sites and other sensitive information. The servers are mostly located with larger providers, so it has become vital that these smaller ISPs choose a reputable large company in order to host their customers data while providing adequate security against malicious attacks. It has become much more feasible in recent months for smaller companies to take the approach of purchasing virtual server space through a larger Tier 1 Internet Service Provider.

Even in recent months ISPs have come under heavy attack from hackers. During February 2000, a group of hackers breached several e-commerce sites in the ‘distributed denial-of-service attacks’ that later hit the FBI site in the USA. This has alerted more organizations to take security issues a lot more seriously.

‘Late last month, more than 400 Internet service providers and corporate security managers formed the Alliance for Internet Security to develop a set of security guidelines for combating distributed denial of-service attacks’

As time goes by and technological advances are made, greater protection will become available for service providers of sensitive information, however unfortunately to every system, no matter how foolproof, a hacker is waiting to breach it. ISPs must stay ahead in order to keep their customers trust or the loss will be extreme.

## Secure Transactions through Encryption

Security issues that ISPs face on a day to day basis does not only include information stored about their customers and web sites, but actual on-line financial transactions. The number of on-line transactions through the Internet has increased dramatically over the last year alone. More and more people are purchasing goods and services online, whether it is ‘business to business’ or ‘business to consumer’ transactions. The need for a secure means of transmitting sensitive information such as credit card details has become the fore front concern of many online merchants.

It has become necessary that consumers know when they transmit their credit card via the Internet, it will travel safely and securely to its final destination. Therefore a lot of time and money has been invested in maximising the security of online transactions throughout the Internet.

In order to transmit sensitive data or information across the Internet without anyone else being able to intercept the transmission is virtually impossible. The best way to combat this problem is through encryption whereby the party who it has initially been sent to can only interpret the information.

The most common methods of encryption on the Internet today for transmission of sensitive data involve ‘Public-Key Cryptography’ and the use of ‘Secure Servers.’

![](images/figure41-1024x401.png)

**Symmetric Key Cryptography**

In the past a technique called PGP (Pretty Good Privacy) or ‘Symmetric Key Cryptography’ was used in order to secure information being transmitted across networks. It basically involved encrypting and decrypting a message using a program called a ‘Key,’ which was used at both ends of the transmission. The key was normally passed to the receiving party during a different transmission and they would be able to use this in order to decrypt the sensitive data. The main problem with this method was that if the encryption program ‘Key’ was stolen during its transmission, the third party would be able to gain unauthorised access to any sensitive data captured through using that key.

**Public Key Cryptography**

With public-key cryptography, separate keys are used to encrypt or decrypt a message, so that nothing but the encrypted message needs to be passed along. Each party in a transaction has a "key pair" which consists of two keys with a particular relationship that allows one to encrypt a message that the other can decrypt. One of these keys is made publicly available and the other is a private key. A message encrypted with a person's public key can't be decrypted with that same key, but can be decrypted with the private key that corresponds to it. If you sign a transaction with your bank using your private key, the bank can read it with your corresponding public key and know that only you could have sent it. This is the equivalent of a digital signature.’

This has been a very successful method for encrypting sensitive information and sending it from one source to another. It has allowed the sender and receiver’s machines to successfully encrypt and decrypt the information so if the transmission was intercepted by a third party, they would have no means by which to decrypt the data because they would have to own the other key.

**Secure Servers (SSL – Secure Socket Layer)**

‘Netscape Corporation has created the best known secure server technologies. It uses a security protocol called Secure Sockets Layer (SSL), which provides data encryption, server authentication, message integrity and optional client authentication for a TCP/IP connection. When a client program connects with a secure server, they exchange a "handshake" which initiates a secure session.’

SSL is technology that allows for the secure transfer of sensitive information over the Internet. It consists of software installed in browsers such as Netscape Navigator and Internet Explorer, as well as the servers. SSL and can be easily obtained by subscribing to a Secured Service Provider or by obtaining a Seller's Certificate and installing it on the existing secured server. Most ISPs offer the service of providing this to the business either through their own services or through larger affiliate links to the ISP.

As mentioned, financial transactions have become a vital part of the Internet and e-commerce as a whole. Currently the majority of transactions carried out online involve the exchange of credit card information. Although the security of the Internet has increased greatly as a whole thanks to ‘Public Key Cryptography’ and the SSL standard, many people are still dubious as to whether or not they can trust this new form of medium to transmit their sensitive information to various e-tailors.

‘A digital certificate is an electronic "credit card" that establishes your credentials when doing business or other transactions on the Web. It is issued by a certification authority (CA). It contains your name, a serial number, expiration dates, a copy of the certificate holder's public key (used for encrypting and decrypting messages and digital signatures), and the digital signature of the certificate-issuing authority so that a recipient can verify that the certificate is real.’

A digital certificate is basically a means of binding details about an individual or organisation to a public key used during an encrypted transmission. There are two main purposes digital certificates have:

- Provides a cryptographic key that allows another party to encrypt information for the certificates owner.
- Provides a measure of proof that the holder of the certificate is who they claim to be – otherwise they will not be able to decrypt any information received.

As we have established it is necessary to obtain a digital certificate before being able to offer secure transactions to consumers of an e-commerce business. When a server presents a certificate during an SSL handshake, the web browser then checks the certificate against its certificate database. If the certificate is already in the browsers database, or if the server certificate is signed by a Certificate Authority whose certificate is in the database, the SSL handshake is then successful.

Due to the introduction of SSL and digital certificates, e-commerce businesses have become more secure on the Internet. More importantly however, consumers trust has began to increase and therefore lead to more transactions being made online. When digital certificates and secure transactions are apparent on a website, more consumers would be less hesitant in giving sensitive information such as credit card details to be transmitted across to the business in question.

It is vital that any ISP providing e-commerce solutions to their customers who will ultimately become e-tailors selling goods and services online, can supply digital certificates and secure servers. Without offering these security services, organisations will take their business elsewhere as any company competing on the Internet for consumers must have their customers peace of mind that any details sent will be as safe as possible.

## Concluding thoughts on Security & Implications of Internet Censorship

It has already started to become clear that the majority of security issues on the Internet have really fallen into the hands of the larger tier 1 network providers. Most smaller ISPs doing business today have tended to opt for the virtual approach through one of the larger providers and hence all security elements have been outsourced to these companies.

The smaller ISP has the responsibility to choose which larger network provider would best suit their needs. In the case of e-commerce solutions, it is vital that the most secure network provider has been chosen to handle secure transactions and they have the ability to hold the security transfer standard of SSL on their servers for the ISPs customer base. This does not necessarily mean that the small to medium sized Virtual ISP outsourcing the physical end of hosting has nothing else to be concerned with. They must be completely familiar with the network provider they are affiliated to and know how to carry out all the processes of setting up secure hosting for their customers as discussed earlier in the chapter. They must also be prepared to supply full support to their clients with the ability to give appropriate training and help when required.

E-Commerce and security have become two different issues that have tended to come together through the implementation of on-line sales through the web. They will continue to grow in the future and the ISP must continue to cater for needs and requirements of their customers as well as researching the newer standards and opportunities that exist within the marketplace today.

It can be argued that censorship is one of the areas that ISPs should be looking into. It has become a serious issue of the Internet offer the last few years as the increased amount of inappropriate material has become available for everyone to access. Many groups have argued that it is the Internet Service Provider that should be looking into these areas and making the net a more secure place for children and other people who may be offended by such material. However it is not the responsibility of the ISP to provide such safeguards to prevent access to sensitive material as they are merely a gateway to the Internet and have no control.

Recently more and more software titles have been made available to combat the problems with access to material on the web. As another form of diversification to target the home users of the ISP, software products could be offered as complimentary to their service. Should small to medium sized ISPs invest in providing more services to the home user when it has been made clear throughout this report that the bulk profits of these companies come from the business world and not the home user?

In conclusion to these issues of security, small to medium ISPs should be able to offer some form of software to combat the problem of censorship, however this should be a very small investment as measured in comparison to their return. It would allow the ISP to show the image of a company that cares and might win over an insignificant amount of home users. The main investment is and should remain to be in the future, security issues for E-commerce and sensitive Business information.
