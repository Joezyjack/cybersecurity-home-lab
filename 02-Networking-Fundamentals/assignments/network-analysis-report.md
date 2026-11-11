Network Analysis and Investigation Report

1. Project Information

Project: Networking Fundamentals Practical Assessment

Operating System: Kali Linux

Tool: Linux Networking Utilities and Nmap 7.99

Assessment Type: Practical Network Investigation

2. Assignment Objective

The objective of this assignment is to demonstrate the ability to investigate a Linux machine’s network configuration, test connectivity, inspect network services and perform basic network reconnaissance.

3. Investigation Tasks

Task 1: Network Interface Discovery

Identify the available network interfaces.

Commands:

ip link show
ip addr show

Questions:

1. How many interfaces were identified?
2. Which interface carried the wireless configuration?
3. What was the assigned IPv4 address?
4. What is the purpose of the loopback interface?

Task 2: IP Addressing

Investigate the machine’s IP addressing configuration.

Commands:

ip addr show
ip route

Questions:

1. What is the machine’s IPv4 address?
2. What is its subnet prefix?
3. What is its subnet mask?
4. What is its network address?
5. What is its broadcast address?

Task 3: Routing Investigation

Identify the default gateway.

Command:

ip route

Questions:

1. What is the default gateway?
2. Which interface is used for external communication?
3. What is the purpose of a routing table?

Task 4: DNS Investigation

Inspect DNS configuration and resolve a domain name.

Commands:

cat /etc/resolv.conf
getent hosts google.com

Questions:

1. Which DNS resolver was configured?
2. Was the domain successfully resolved?
3. What is the difference between IPv4 and IPv6 DNS responses?

Task 5: Connectivity Testing

Test local and external connectivity.

Commands:

ping -c 4 192.168.100.1
ping -c 4 8.8.8.8

Questions:

1. Did the gateway respond?
2. Did the external IP respond?
3. Was packet loss observed?
4. What does network latency mean?

Task 6: Port and Service Inspection

Inspect network sockets.

Commands:

ss -tuln
ss -tun
sudo ss -tulpn

Questions:

1. What is a listening port?
2. What is the difference between TCP and UDP?
3. What is the purpose of port 443?
4. What is the difference between listening and established connections?

Task 7: Nmap Reconnaissance

Perform a localhost scan.

Commands:

nmap --version
nmap 127.0.0.1
nmap -sV 127.0.0.1
nmap -p- 127.0.0.1

Questions:

1. Which Nmap version was installed?
2. Was localhost identified as online?
3. How many ports were examined in the default scan?
4. How many ports were examined in the full TCP scan?
5. What does a closed port mean?
6. What does service version detection accomplish?

4. Investigation Summary

The practical investigation identified the Kali Linux network interfaces and established that the wireless interface was carrying the active network configuration.

The IPv4 address, subnet prefix, default gateway and DNS resolver were successfully identified.

Connectivity tests confirmed communication with the local gateway and an external IP address.

DNS resolution successfully returned an IPv6 address for google.com.

Socket inspection provided information about active connections and listening services.

Nmap scans against localhost reported all scanned TCP ports closed.

5. Security Recommendations

1. Regularly inspect active network interfaces.
2. Monitor listening services.
3. Disable unnecessary network services.
4. Keep network-related software updated.
5. Use appropriate firewall rules.
6. Review DNS configuration.
7. Document unusual network behaviour.
8. Perform authorized network assessments periodically.

6. Assessment Conclusion

The assignment demonstrates practical knowledge of Linux networking and basic network reconnaissance.

The exercises provided experience with IP addressing, DNS, routing, connectivity testing, network sockets and Nmap.

These skills establish a foundation for more advanced cybersecurity exercises involving network discovery, service enumeration and penetration testing.

Assessment: Networking Fundamentals
Platform: Kali Linux
Portfolio: Cybersecurity Home Lab
