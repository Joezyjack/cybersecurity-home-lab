Exercise 06: Network Troubleshooting

1. Introduction

Network troubleshooting is the process of identifying, diagnosing and resolving problems that affect network communication.

In this exercise, I used Kali Linux networking utilities to examine network connectivity between my computer, the local gateway and an external destination.

I also tested DNS resolution.

2. Objectives

* Understand basic network troubleshooting.
* Test communication with the default gateway.
* Test external IP connectivity.
* Verify DNS resolution.
* Interpret packet loss.
* Understand response-time statistics.
* Identify common network connectivity problems.

3. Laboratory Environment

* Operating System: Kali Linux
* Network interface: wlan0
* IPv4 address: 192.168.100.193
* Default gateway: 192.168.100.1
* External test destination: 8.8.8.8

4. Commands Executed

Test local gateway connectivity

ping -c 4 192.168.100.1

This sends four ICMP echo requests to the default gateway.

Test external IP connectivity

ping -c 4 8.8.8.8

This tests communication with an external IP address.

Test DNS resolution

getent hosts google.com

This checks whether the system can resolve a domain name.

Inspect routing information

ip route

Displays the routing table and default gateway.

5. Practical Test Results

Test 1: Local Gateway

Target:

192.168.100.1

Observed result:

4 packets transmitted
4 received
0% packet loss

Finding:

The Kali Linux machine successfully communicated with its default gateway.

Test 2: External Connectivity

Target:

8.8.8.8

Observed result:

4 packets transmitted
4 received
0% packet loss

Finding:

The machine successfully communicated with the external IP address.

Test 3: DNS Resolution

Command:

getent hosts google.com

Observed result:

2c0f:fb50:4003:805::200e google.com

Finding:

The system successfully resolved google.com to an IPv6 address.

6. Understanding Ping Statistics

The external connectivity test produced the following statistics:

Measurement	Result
Minimum response time	56.734 ms
Average response time	122.147 ms
Maximum response time	266.992 ms
Mean deviation	84.528 ms
Packet loss	0%

Explanation

Minimum: The fastest recorded response.

Average: The average response time across the four successful replies.

Maximum: The slowest recorded response.

Mean deviation: A measure of variation in response times.

Packet loss: The percentage of transmitted packets that did not receive a reply.

The results showed successful connectivity with variable response times.

7. Findings and Analysis

The connectivity tests established the following:

1. The local gateway was reachable.
2. External IP connectivity was successful.
3. DNS resolution was successful.
4. Both ping tests recorded zero packet loss.
5. External response times varied during the test.

These observations indicated that the Kali machine had working local and external network connectivity during the exercise.

8. Common Network Troubleshooting Commands

The following commands are useful for future network investigations.

Inspect network interfaces

ip link show

Inspect IP addresses

ip addr show

Inspect routing information

ip route

Inspect DNS configuration

cat /etc/resolv.conf

Test gateway connectivity

ping -c 4 192.168.100.1

Test external connectivity

ping -c 4 8.8.8.8

Test domain resolution

getent hosts google.com

Inspect network sockets

ss -tuln

9. Troubleshooting Scenarios

Scenario 1: Gateway Unreachable

Possible causes:

* Wireless disconnection.
* Incorrect IP configuration.
* Gateway unavailable.
* Network interface disabled.

Recommended investigation:

ip addr show
ip route
ping -c 4 192.168.100.1

Scenario 2: External IP Unreachable

Possible causes:

* Router has no internet connection.
* Incorrect routing.
* Firewall restrictions.
* ISP connectivity problems.

Recommended investigation:

ip route
ping -c 4 8.8.8.8

Scenario 3: DNS Resolution Failure

Possible causes:

* DNS resolver unavailable.
* Incorrect DNS configuration.
* Network connectivity problems.

Recommended investigation:

cat /etc/resolv.conf
getent hosts google.com

Scenario 4: High Network Latency

Possible causes:

* Network congestion.
* Wireless interference.
* Long routing paths.
* Temporary network instability.

Recommended investigation:

ping -c 10 8.8.8.8

Compare the response times and packet loss.

10. Security Significance

Network troubleshooting is important in cybersecurity because connectivity problems can sometimes indicate:

* Incorrect firewall configuration.
* Network segmentation problems.
* DNS misconfiguration.
* Unexpected routing changes.
* Network availability issues.

A systematic troubleshooting process helps distinguish ordinary connectivity problems from potential security issues.

11. Learning Outcomes

Through this exercise, I learned how to:

* Test local network connectivity.
* Verify external IP connectivity.
* Investigate DNS resolution.
* Interpret ICMP responses.
* Analyse packet loss and latency.
* Use Linux networking commands for troubleshooting.

12. Conclusion

The network troubleshooting exercise was successfully completed.

The Kali Linux machine communicated with its default gateway and an external IP address, while DNS resolution returned an IPv6 address for google.com.

The exercise provided practical experience in network diagnostics and strengthened my understanding of Linux network troubleshooting.

Module: Networking Fundamentals
Exercise: Network Troubleshooting
Platform: Kali Linux
