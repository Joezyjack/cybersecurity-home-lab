Exercise 01: Network Interface Discovery

Objective

Identify the hostname, network interfaces, IP addresses and MAC addresses of the Kali Linux machine.

Commands Executed

hostname
ip link show
ip addr show

Observations

1. Hostname: kali
2. Loopback interface: lo
3. Ethernet interface: eth0
4. Wireless interface: wlan0
5. Wireless IPv4 address: 192.168.100.193
6. Wireless subnet prefix: /24
7. Ethernet status: DOWN
8. Wireless interface status: UP

Findings

The Kali Linux machine has three identified network interfaces: loopback, Ethernet and wireless.

The wireless interface has an assigned private IPv4 address and is the interface currently configured for wireless networking.

The Ethernet interface is enabled but does not have an active physical network carrier.

Learning Outcome

I learned how to identify Linux network interfaces, inspect their operational states, distinguish between IPv4 and MAC addresses, and interpret basic network configuration information.

Environment: Kali Linux
Module: Networking Fundamentals
Exercise: Network Interface Discovery
