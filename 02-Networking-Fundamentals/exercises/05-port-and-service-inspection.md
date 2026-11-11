Exercise 04: TCP, UDP and Network Port Inspection

Objective

Inspect network sockets, identify active connections and understand common network services using Kali Linux.

Commands Executed

ss -tuln
ss -tun
grep -E '^(ssh|http|https|domain|ftp)[[:space:]]' /etc/services
sudo ss -tulpn

Observations

1. The listening socket inspection did not display any listening entries.
2. The active connection inspection displayed established TCP connections.
3. Three TCP connections used remote port 443.
4. A UDP connection to the local gateway was displayed.
5. The services database listed common ports for FTP, SSH, DNS, HTTP and HTTPS.
6. The administrative listening socket inspection displayed no listening entries.

Findings

The Kali machine had active outbound network connections during the inspection.

The TCP connections used HTTPS-associated remote ports, while the local ports were temporary client-side ports.

No listening TCP or UDP sockets were reported in the captured listening socket inspections.

The /etc/services file provided a reference for commonly assigned service ports.

Security Significance

Unnecessary listening services can increase a computer’s attack surface.

Regular socket inspection helps administrators identify services that may require security review.

Learning Outcomes

* Understood TCP and UDP socket inspection.
* Differentiated listening sockets from established connections.
* Identified common network ports.
* Learned how to inspect active connections.
* Understood the security importance of exposed services.

Conclusion

This exercise provided practical experience inspecting network sockets and understanding the relationship between network protocols, ports and services.

The findings represent the machine’s observed state during the exercise, not a permanent assessment of its network exposure.

Platform: Kali Linux
Module: Networking Fundamentals
Exercise: TCP, UDP and Network Port Inspection


Exercise 05: Port and Service Inspection

1. Introduction

Network ports are communication endpoints that allow applications and services to exchange information across a network.

In this exercise, I investigated TCP and UDP sockets, listening services and established connections using Kali Linux.

2. Objectives

* Understand network ports.
* Differentiate TCP and UDP.
* Identify listening sockets.
* Inspect established network connections.
* Understand common service ports.
* Recognize potential network exposure.

3. Commands Executed

Display listening sockets

ss -tuln

Display active connections

ss -tun

Display service definitions

grep -E '^(ssh|http|https|domain|ftp)[[:space:]]' /etc/services

Inspect listening sockets with process details

sudo ss -tulpn

4. Observations

The listening socket inspection displayed no listening TCP or UDP entries at the time of testing.

The active connection inspection showed:

* Established TCP connections using remote port 443.
* A UDP connection involving the local gateway at 192.168.100.1, port 67.

The service definitions file was also inspected to identify commonly assigned ports.

5. Common Network Ports

Port	Protocol	Service
21	TCP	FTP
22	TCP	SSH
23	TCP	Telnet
25	TCP	SMTP
53	TCP/UDP	DNS
80	TCP	HTTP
443	TCP	HTTPS
3306	TCP	MySQL
3389	TCP	Remote Desktop

6. Understanding TCP and UDP

TCP

Transmission Control Protocol is connection-oriented and provides reliable, ordered data delivery.

It is commonly used by web applications, SSH and file transfer services.

UDP

User Datagram Protocol is connectionless and does not guarantee delivery or ordering.

It is commonly used for DNS queries, voice communication and real-time applications.

7. Understanding Port States

State	Explanation
Open	A service is accepting connections
Closed	No service is listening on the port
Filtered	Filtering prevents Nmap from determining the state

8. Findings

The listening socket inspection did not report listening entries during the captured test.

The active connection inspection displayed outgoing TCP connections using remote port 443.

The UDP output showed communication involving the local gateway.

The results demonstrated the difference between active connections and listening services.

9. Security Significance

Listening services can increase the attack surface of a computer.

Administrators should identify unnecessary services, review their configurations and restrict access where appropriate.

10. Learning Outcomes

* Learned to inspect TCP and UDP sockets.
* Differentiated listening sockets from established connections.
* Identified common service ports.
* Understood basic network exposure.
* Learned the security importance of service inspection.

11. Conclusion

The exercise provided practical experience in inspecting network sockets and understanding network ports and services.

The results describe the network state observed during the laboratory session.

Platform: Kali Linux
Module: Networking Fundamentals
Exercise: Port and Service Inspection
