Exercise 01: Network Interface Discovery

1. Introduction

Network interface discovery is the process of identifying the network interfaces available on a computer and examining their operational status and configuration.

In this exercise, I used Kali Linux terminal commands to inspect the network interfaces on my system.

2. Objectives

* Identify available network interfaces.
* Understand the purpose of network interfaces.
* Identify active and inactive interfaces.
* Inspect IPv4 and IPv6 addresses.
* Identify MAC addresses.
* Understand the loopback interface.

3. Laboratory Environment

* Operating System: Kali Linux
* Hardware: Dell Latitude laptop
* Network connection: Wireless
* Interface inspection tool: Linux IP utility

4. Commands Executed

Identify the hostname

    hostname

Displays the hostname of the computer.

Display network interfaces

    ip link show

Displays available network interfaces and their operational states.

Display interface addresses

    ip addr show

Displays IP addresses, MAC addresses and other interface information.

5. Network Interfaces Identified

Three network interfaces were identified during the exercise.

  A. Loopback Interface (lo)

The loopback interface is used for communication within the local computer.

Observed IPv4 address:

  127.0.0.1

The loopback interface allows applications and services to communicate with the same machine without using an external network.


B. Ethernet Interface (eth0)

The Ethernet interface represents the wired network connection.

    Observed status:

NO-CARRIER
state DOWN

This indicated that the interface was enabled but did not detect an active physical network connection.

C. Wireless Interface (wlan0)

The wireless interface was the active network interface used for network communication.

Observed IPv4 address:

192.168.100.193/24

The interface displayed:

UP
LOWER_UP

Its state was also reported as DORMANT.

This interface was associated with the wireless network connection.

6. Findings

Component	Observed result
Hostname	kali
Loopback interface	lo
Ethernet interface	eth0
Wireless interface	wlan0
Active network interface	wlan0
Wireless IPv4 address	192.168.100.193/24
Ethernet status	DOWN
Loopback IPv4	127.0.0.1

The wireless interface was identified as the interface carrying the active network configuration.

7. Security Significance

Understanding network interfaces is important in cybersecurity because network interfaces determine how a computer communicates with other devices.

Security administrators should understand:

* Which interfaces are active.
* Which interfaces are connected to external networks.
* Which IP addresses are assigned.
* Whether unnecessary interfaces should be disabled.

8. Learning Outcomes

Through this exercise, I learned how to:

* Identify Linux network interfaces.
* Inspect interface operational states.
* Differentiate Ethernet and wireless interfaces.
* Identify IPv4 and MAC addresses.
* Understand the purpose of the loopback interface.

9. Conclusion

The exercise provided practical experience in inspecting network interfaces using Kali Linux.

I successfully identified the loopback, Ethernet and wireless interfaces and determined that wlan0 was the interface carrying my wireless network configuration.

Module: Networking Fundamentals
Exercise: Network Interface Discovery
Platform: Kali Linux
