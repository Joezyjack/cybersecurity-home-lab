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
