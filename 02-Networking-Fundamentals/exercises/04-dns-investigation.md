Exercise 04: DNS Investigation

1. Introduction

Domain Name System (DNS) is a fundamental component of computer networking.

DNS translates human-readable domain names into IP addresses that computers use to communicate.

For example, instead of remembering the IP address of a website, users can enter a domain name such as:

google.com

DNS helps determine the corresponding IP address.

In this exercise, I investigated DNS configuration and performed domain name resolution tests using Kali Linux.

2. Objectives

* Understand the purpose of DNS.
* Identify the configured DNS resolver.
* Inspect DNS configuration.
* Perform domain name resolution.
* Understand IPv4 and IPv6 DNS responses.
* Learn basic DNS troubleshooting.

3. Laboratory Environment

* Operating System: Kali Linux
* Network interface: wlan0
* DNS configuration utility: resolv.conf
* DNS testing utility: getent

4. Commands Executed

Inspect DNS configuration

cat /etc/resolv.conf

Displays the DNS resolver configuration.

Resolve a domain name

getent hosts google.com

Uses the system’s configured name service to retrieve address information for the specified hostname.

Inspect the routing and DNS configuration

ip route

Displays the routing table and default gateway.

5. DNS Configuration Findings

The DNS configuration displayed:

nameserver 192.168.100.1

This indicates that my Kali Linux machine was configured to use 192.168.100.1 as its DNS resolver.

The address was also identified as the default gateway.

6. DNS Resolution Test

Command executed:

getent hosts google.com

Observed result:

2c0f:fb50:4003:805::200e google.com

Interpretation

The command successfully returned an IPv6 address associated with google.com.

This confirmed that the system was able to resolve the domain name using its configured name service.

7. Understanding DNS Record Types

DNS supports different record types.

Record	Purpose
A	Maps a hostname to an IPv4 address
AAAA	Maps a hostname to an IPv6 address
MX	Identifies mail exchange servers
CNAME	Creates an alias for another hostname
NS	Identifies authoritative name servers
TXT	Stores text information associated with a domain

These records are important for understanding how internet services are configured.

8. Security Significance

DNS is an important area of cybersecurity because attackers may attempt to exploit weaknesses in DNS configuration or manipulate domain resolution.

Security professionals investigate DNS to:

* Identify suspicious domain lookups.
* Investigate malicious domains.
* Detect DNS misconfigurations.
* Understand domain infrastructure.
* Monitor unusual DNS traffic.

9. Learning Outcomes

Through this exercise, I learned how to:

* Inspect DNS resolver configuration.
* Identify the configured DNS server.
* Resolve domain names using getent.
* Recognize IPv6 DNS responses.
* Understand common DNS record types.
* Appreciate the security importance of DNS.

10. Conclusion

The DNS investigation successfully identified the configured resolver and demonstrated that google.com could be resolved to an IPv6 address.

This exercise strengthened my understanding of DNS configuration and domain name resolution in Linux.

Module: Networking Fundamentals
Exercise: DNS Investigation
Platform: Kali Linux
