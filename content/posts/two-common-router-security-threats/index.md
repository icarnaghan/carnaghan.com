---
author: "icarnaghan"
title: "Two Common Router Security Threats"
date: 2016-10-11
categories: 
  - "cybersecurity"
tags: 
  - "csec-640"
---

_Syn Flood or Denial of Service Attack_

Syn Flood attacks, often referred to as Denial of Service Attacks are caused through exploitation of the TCP protocol. The attacker sends a large number of TCP/SYN packets using a forged address. Because of this, the destination server is unable to successfully establish a proper connection due to the source being unreachable. Lawrence (n.d.). Each time the server attempts to establish a connection, resources are used up with the flooding of packets causing eventual slow down or non-responsiveness.

There are different methods that can be used to mitigate these types of attacks. One common mitigation strategy is called blackholing, where the service provider diverts all traffic into a ‘black hole’ in an effort to save resources. Cisco (2014). The problem with this strategy is that legitimate packets are also lost in the process. Access Control Lists is another method to control incoming traffic as well as firewalls. In their paper, Ioannidis & Bellovin (2002) discussed the implementation of Pushback, a process where functionality is added to each router to detect and preferentially drop packets that ‘probably’ belong to an attack.

_Brute Force_

Brute force attacks can occur when routers are subjected to an attacker attempting to guess the password and gain unauthorized access. These types of attacks can be used in conjunction with automated guessing tools and dictionary methods in order to attempt to crack the password.

There are several methods for defending against brute force attacks. Lockouts can be used to prevent too many password retries. Drawbacks of lockouts however include potential denial of service, diversion tactics by the attackers, and overall inefficiency. Better ways to deal with these types of attacks include injecting random pauses between retries, sending success HTTP 200 success codes to confuse the attacker instead of the typical 401, and better use of security or secret questions. System Administration Database (2007).

References:

System Administration Database. (2007) Blocking Brute Force Attacks. Retrieved from: http://www.cs.virginia.edu/~csadmin/gen\_support/brute\_force.php

Lawrence, M. (n.d.) Types of Attacks on Routers. Studio D. Retreived from: http://smallbusiness.chron.com/types-attacks-routers-71576.html

Cisco (2014). Defeating DDOS Attacks. Retrieved from: http://www.cisco.com/c/en/us/products/collateral/security/traffic-anomaly-detector-xt-5600a/prod\_white\_paper0900aecd8011e927.html

Ioannidis, J., & Bellovin, S. M., (2002). Implementing Pushback: Router-Based Defense Against DDoS Attacks. Retrieved from http://www.thefengs.com/wuchang/courses/cse5xx\_OGI/cse581\_winter2002/papers/pushback-impl.pdf
