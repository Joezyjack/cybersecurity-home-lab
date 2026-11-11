Networking Fundamentals — Cybersecurity Home Lab

1. Overview

This module focuses on understanding computer networking and developing practical network investigation skills using Kali Linux.

It introduces fundamental networking concepts and Linux commands used to inspect network interfaces, IP addresses, routing tables, DNS configuration, network connectivity, TCP/UDP protocols and network services.

The module also introduces Nmap for basic network reconnaissance and port scanning.

2. Learning Objectives

By completing this module, I aim to:

* Understand basic computer networking concepts.
* Identify network interfaces and their operational states.
* Understand IPv4 and IPv6 addressing.
* Interpret subnet masks and CIDR notation.
* Identify default gateways and routing information.
* Investigate DNS configuration and resolution.
* Test network connectivity using ICMP.
* Understand TCP and UDP communication.
* Inspect active connections and listening ports.
* Perform basic network reconnaissance using Nmap.
* Interpret network scanning results.
* Document findings and recommend appropriate security improvements.

3. Laboratory Environment

Component	Configuration
Operating system	Kali Linux
Computer	Dell Latitude laptop
Network connection	Wi-Fi
Wireless interface	wlan0
Network utility	iproute2
Connectivity tool	ping
Socket inspection	ss
Reconnaissance tool	Nmap 7.99

4. Module Structure

02-Networking-Fundamentals/
│
├── README.md
├── commands.md
├── findings.md
│
├── exercises/
│   ├── 01-network-interface-discovery.md
│   ├── 02-ip-addressing.md
│   ├── 03-network-connectivity.md
│   ├── 04-dns-investigation.md
│   ├── 05-port-and-service-inspection.md
│   ├── 06-network-troubleshooting.md
│   └── 07-nmap-localhost-scan.md
│
├── assignments/
│   └── network-analysis-report.md
│
└── screenshots/

5. Practical Exercises

Exercise 01: Network Interface Discovery

Identified the loopback, Ethernet and wireless interfaces using Linux networking commands.

Exercise 02: IP Addressing

Investigated IPv4 addressing, subnet prefixes, private IP addresses and network configuration.

Exercise 03: Network Connectivity

Tested communication with the local gateway and an external IP address.

Exercise 04: DNS Investigation

Inspected DNS resolver configuration and performed domain name resolution.

Exercise 05: Port and Service Inspection

Investigated listening sockets, established connections and common network service ports.

Exercise 06: Network Troubleshooting

Applied Linux networking commands to investigate connectivity, routing, DNS and network response times.

Exercise 07: Nmap Localhost Scanning

Installed and verified Nmap, scanned the local machine and investigated TCP port states.

6. Tools and Commands Practised

* ip
* ping
* getent
* ss
* grep
* cat
* nmap
* sudo

7. Security Concepts Learned

* Network interface identification
* IPv4 and IPv6 addressing
* Subnetting
* Default gateways
* DNS resolution
* Routing
* TCP and UDP
* Network ports
* Listening services
* Network reconnaissance
* Port scanning
* Attack surface identification

8. Key Practical Findings

The Kali Linux machine used the wireless interface wlan0 with an observed IPv4 address of 192.168.100.193/24.

The default gateway and configured DNS resolver were both identified as 192.168.100.1.

Connectivity testing recorded successful communication with the gateway and external IP address 8.8.8.8, with zero packet loss in both four-packet tests.

DNS resolution successfully returned an IPv6 address for google.com.

Nmap 7.99 was installed and verified. A localhost scan identified the machine as online and reported all 1,000 default TCP ports closed. A subsequent full TCP scan reported all 65,535 TCP ports closed.

These observations describe the laboratory results at the time of testing.

9. Learning Outcomes

This module strengthened my understanding of Linux networking and provided practical experience in inspecting network configurations, testing connectivity, investigating network services and interpreting Nmap results.

10. Next Learning Phase

The next phase will focus on:

* Advanced Nmap scanning.
* Network discovery.
* Service enumeration.
* Network mapping.
* Web application fundamentals.
* Authorized penetration testing in an isolated laboratory.

⸻

Portfolio: Cybersecurity Home Lab
Module: 02 — Networking Fundamentals
Platform: Kali Linux
Status: Practical exercises documented; further laboratory exercises planned.
