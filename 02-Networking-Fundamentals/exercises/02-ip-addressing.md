Exercise 02: IP Addressing and Subnet Identification

1. Introduction

IP addressing is a fundamental concept in computer networking.

An Internet Protocol (IP) address is a logical address assigned to a network interface to enable communication between devices.

In this exercise, I investigated the IPv4 configuration of my Kali Linux machine and learned how subnet prefixes, network addresses and broadcast addresses work.

2. Objectives

* Understand IPv4 addressing.
* Identify the assigned IP address.
* Understand subnet masks and CIDR notation.
* Identify network and broadcast addresses.
* Understand private IP addressing.
* Distinguish between IPv4 and IPv6.

3. Laboratory Environment

* Operating System: Kali Linux
* Network interface: wlan0
* Network utility: ip

4. Commands Executed

Display IP configuration

ip addr show

Displays assigned IP addresses and network interface information.

Display routing information

ip route

Displays the routing table, including the default gateway and connected networks.

Display detailed interface information

ip -br addr

Displays network interfaces and their addresses in a simplified format.

5. IP Address Observations

My Kali Linux machine displayed the following wireless IPv4 configuration:

192.168.100.193/24

The address was assigned to the wlan0 interface.

Understanding the IP address

Component	Value
IPv4 address	192.168.100.193
CIDR prefix	/24
Subnet mask	255.255.255.0
Network address	192.168.100.0
Broadcast address	192.168.100.255

What does /24 mean?

The /24 notation is known as Classless Inter-Domain Routing (CIDR).

It indicates that the first 24 bits identify the network portion of the address.

The equivalent subnet mask is:

255.255.255.0

For a conventional IPv4 /24 subnet, there are 256 total addresses, with 254 normally available for host assignment.

6. Understanding Private IP Addresses

The address 192.168.100.193 belongs to the private IPv4 address range:

192.168.0.0 - 192.168.255.255

Private IP addresses are commonly used in homes, offices and internal organizational networks.

They are not directly routable across the public internet.

7. IPv4 and IPv6

During network inspection, both IPv4 and IPv6 addresses were observed.

IPv4

Example:

192.168.100.193

IPv4 uses 32-bit addresses.

IPv6

IPv6 uses 128-bit addresses and provides a much larger address space.

An IPv6 address was also assigned to the wireless interface during the exercise.

8. Findings

The Kali Linux wireless interface received a private IPv4 address with a /24 network prefix.

The configuration corresponds to the network 192.168.100.0/24.

This established the network addressing information required for subsequent routing, DNS and connectivity exercises.

9. Security Significance

IP addressing is important in cybersecurity because it helps security professionals:

* Identify devices on networks.
* Understand network boundaries.
* Identify communication paths.
* Investigate suspicious network traffic.
* Configure firewall rules.
* Perform authorized network discovery.

10. Learning Outcomes

Through this exercise, I learned how to:

* Inspect IP addresses using Linux commands.
* Interpret CIDR notation.
* Understand subnet masks.
* Identify network and broadcast addresses.
* Distinguish private and public IP addressing.
* Recognize IPv4 and IPv6 configurations.

11. Conclusion

This exercise provided practical knowledge of IP addressing and subnet identification using Kali Linux.

Understanding IP addressing establishes an important foundation for network troubleshooting, network reconnaissance and penetration testing.

Module: Networking Fundamentals
Exercise: IP Addressing and Subnet Identification
Platform: Kali Linux
