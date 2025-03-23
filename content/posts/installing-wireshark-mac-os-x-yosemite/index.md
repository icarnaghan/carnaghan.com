---
author: "icarnaghan"
title: "Installing Wireshark on Mac OS X (Yosemite)"
date: 2016-09-18
categories: 
  - "cybersecurity"
tags: 
  - "csec-640"
---

Wireshark is a software application for protocol and network traffic analysis, also known as a network sniffer. The application can be downloaded for free at https://www.wireshark.org/#download. I downloaded Wireshark from the url and selected the macOS 10.6 .dmg file. I was able to successfully mount the download image and run the package installer which kept all the default settings with the following installed in my system:

- _/Applications/Wireshark.app_. The main Wireshark application.
- _/Library/LaunchDaemons/org.wireshark.ChmodBPF.plist_. A launch daemon that adjusts permissions on the system's packet capture devices (_/dev/bpf_\*) when the system starts up.
- _/Library/Application Support/Wireshark/ChmodBPF_ A copy of the launch daemon property list, and the script that the launch daemon runs.
- _/usr/local/bin_. A wrapper script and symbolic links which will let you run Wireshark and its associated utilities from the command line. You can access them directly or by adding /usr/local/bin to your PATH if it's not already in your PATH.

(Source: Wireshark Read Me First.rtf)

Within the Wireshark application display filters can be applied to all traffic by selecting from a pre-defined list already bundled with the application, or by adding addition filters. Display filters let you compare the fields within a protocol against a specific value, compare fields against fields, and check the existence of specified fields or protocols. Wireshark (ND).

The following list contains some filters that can be used to research and analyze traffic.

| Display filter | Explanation | Example |
| --- | --- | --- |
|  tcp.port | Shows only the packets with a matching port number, in this case only traffic on port 25. | tcp.port eq 25 |
| ip.src | Excludes traffic matching a source IP address of 192.168.33.10 | ip.src != 192.168.33.10 |
| ip.dst | Include packets with a matching destination IP address of 10.0.4.2 | ip.dst == 10.0.4.2 |
| Tcp.port \|\| udp.port | Displays traffic that either has a UDP port of 80 or a TCP port of 80 | tcp.port == 80 \|\| udp.port == 80 |
| Ip.address and not tcp.port | Filters only SMTP (Port 25) traffic from 192.168.33.10 | Ip.addr == 192.168.33.10 and not tcp.port 25 |

 

References:

- Wireshark. (N.D.) _Wireshark Filters_. Retrieved from: https://www.wireshark.org/docs/man-pages/wireshark-filter.html.
- Greer, C. (2010). _Top 10 Wireshark Filters_. Retrieved from: http://www.lovemytool.com/blog/2010/04/top-10-wireshark-filters-by-chris-greer.html
