---
author: "icarnaghan"
title: "TCP Congestion Control"
date: 2016-09-18
categories: 
  - "cybersecurity"
tags: 
  - "csec-640"
---

So it's that time of year again where I decided to enroll in another Cybersecurity class at UMUC. I will be posting snippets from the class over the next few weeks. This week TCP Congestion Control was one of the topics I was looking at and so this post will serve as a high level overview.

TCP Congestion Control is the process of monitoring and controlling network traffic in order to avoid congestion, which could lead to potential loss of packets and / or poor transmission rates. It determines the available capacity on the network and in turn is equipped with the information needed to know the number of packets that can be safely transmitted. Congestion control maintain a state variable for each connection called a congestion window, which is used to determine limits on the amount of data that can be sent at any given time. The size of the limits defined in this window change accordingly based on congestion levels via the process of the additive increase/multiplicative decrease (AIMD) algorithm. AIMD essentially lowers the limits of the congestion window when there is less congestion and raises them when congestion levels have increased.

In their 1999 paper, Allman & Paxson define several of the different algorithms TCP uses in order to perform congestion control. These include slow start, congestion avoidance, fast retransmit, and fast recovery. Slow start operates by monitoring  the rate of previous requests and transactions and uses this information to adjust transmission rates in order to avoid congestion. The purpose of slow start is to increase the congestion window rapidly from a cold start in TCP connections. A slow start threshold variable is used to determine whether slow start or congestion avoidance should be implemented. If the congestion window is lower than the slow start threshold, then the slow start algorithm is used, otherwise congestion avoidance is implemented. Allman & Paxson (1999). Two other common algorithms associated with TCP congestion control include the Fast Retransmit and Fast Recovery, which are used to bypass slow start and avoidance used in cases of retransmitting lost data.

References:

- Allman, M., Paxson, V., & W. Stevens. (1999). TCP Congestion Control", RFC 2581, April 1999. Retrieved from: https://www.rfc-editor.org/rfc/rfc5681.txt
- SSF Research Network. (n.d.). TCP tutorial. Retrieved from http://ssfnet.org/Exchange/tcp/tcpTutorialNotes.html
