Networking Fundamentals — Project Findings

1. Project Overview

This document summarizes the practical findings from the Networking Fundamentals module conducted using Kali Linux.

The exercises focused on network interface discovery, IP addressing, routing, DNS investigation, connectivity testing, socket inspection and Nmap reconnaissance.

2. Network Interface Findings

Three network interfaces were identified:

Interface	Description	Observed status
lo	Loopback	UP
eth0	Ethernet	DOWN / NO-CARRIER
wlan0	Wireless	UP / LOWER_UP

The wireless interface was carrying the active network configuration.

Observed wireless IPv4 address:

192.168.100.193/24

3. IP Addressing Findings

The wireless interface used a private IPv4 address.

Parameter	Observed value
IP address	192.168.100.193
CIDR prefix	/24
Subnet mask	255.255.255.0
Network address	192.168.100.0
Broadcast address	192.168.100.255

4. Routing Findings

The routing table identified:

* Default gateway: 192.168.100.1
* Network interface: wlan0
* Source IP: 192.168.100.193

The route inspection confirmed that Linux selected the wireless interface and default gateway for the external destination 8.8.8.8.

5. DNS Findings

The configured DNS resolver was:

192.168.100.1

The command getent hosts google.com successfully returned an IPv6 address.

Observed result:

2c0f:fb50:4003:805::200e

6. Connectivity Findings

Two ICMP connectivity tests were completed.

Test	Packets transmitted	Packets received	Packet loss
Gateway	4	4	0%
External IP	4	4	0%

The gateway responded successfully, and external IP connectivity was also confirmed.

The external ping test recorded varying response times.

7. Port and Service Inspection Findings

The following commands were used:

ss -tuln
ss -tun
sudo ss -tulpn

The listening socket inspections displayed no listening entries at the time of observation.

The active connection inspection displayed established TCP connections using remote port 443 and a UDP connection involving the local gateway.

The /etc/services file was inspected to understand common service-to-port assignments.

8. Nmap Findings

Nmap version 7.99 was installed and verified.

Default localhost scan

Command:

nmap 127.0.0.1

Result:

* Host identified as up.
* 1,000 TCP ports scanned.
* 1,000 ports closed.
* No open ports identified.

Service version detection

Command:

nmap -sV 127.0.0.1

Result:

* Scan completed successfully.
* No open ports were discovered among the default 1,000 TCP ports.
* No service versions were identified.

Full TCP port scan

Command:

nmap -p- 127.0.0.1

Result:

* 65,535 TCP ports scanned.
* 65,535 ports closed.
* No open TCP ports identified.

9. Security Observations

The exercises demonstrated the importance of:

1. Knowing which network interfaces are active.
2. Understanding IP addressing and network boundaries.
3. Identifying default gateways and DNS resolvers.
4. Testing network connectivity systematically.
5. Inspecting listening network services.
6. Identifying unnecessary network exposure.
7. Understanding the limitations of port scanning.

The localhost scan did not identify open TCP ports, but this does not establish that the machine is completely secure.

10. Overall Conclusion

The Networking Fundamentals module provided practical experience in Linux network inspection, connectivity testing, DNS investigation, socket inspection and basic network reconnaissance.

The practical findings established a foundation for further learning in network discovery, service enumeration, vulnerability assessment and penetration testing.

Platform: Kali Linux
Tool: Nmap 7.99
Module: Networking Fundamentals
