
# Exercise 05: UDP Port Scanning

## Objective

Identify selected UDP ports on an authorized lab device.

## Explanation

UDP stands for User Datagram Protocol.

It is a connectionless transport protocol and does not use the TCP three-way handshake.

## Step 1: Perform UDP Scan

```bash
sudo nmap -sU --top-ports 20 <AUTHORIZED_TARGET_IP>
```

## Step 2: Save Results

```bash
sudo nmap -sU --top-ports 20 <AUTHORIZED_TARGET_IP> -oN udp-scan.txt
```

## Understanding UDP States

- Open: A UDP service responded.
- Closed: The target reported that the port was unreachable.
- Open|filtered: Nmap cannot determine whether the port is open or filtered.

## Questions

1. What does UDP stand for?
It is a transport-layer protocol used to send data between devices over a network without establishing a connection first

2. How does UDP differ from TCP?
   
TCP
Connection-oriented	
Reliable delivery
Acknowledgments are used	
Packets are sequenced	
More overhead	
Used for HTTPS, SSH, etc.	

UDP
Connectionless
Delivery is not guaranteed
No standard delivery acknowledgments
No guaranteed packet ordering
Lower overhead, generally faster
Used for DNS, streaming, gaming, etc.

Simple analogy:
- TCP: Sending a registered parcel with tracking and delivery confirmation.
- UDP: Sending a postcard without confirmation that it arrived.

3. Why can UDP scans take longer?
UDP scans can take longer because many UDP services do not respond when they receive an unexpected or empty probe.
Nmap may have to:
- Wait for a response or timeout.
- Retransmit probes.
- Distinguish silent ports from filtered ports.
- Process ICMP responses, which may be rate-limited by devices.
This makes UDP scanning potentially slower than TCP scanning, especially when many ports are scanned.

4. Explain open|filtered.
open|filtered is an Nmap UDP scan result meaning Nmap cannot determine whether the port is open or filtered.

This happens because there is no response to the probe.

The port could be:
- Open: A UDP service is running but doesn't respond to the probe.
- Filtered: A firewall is blocking the probe or response.
Nmap cannot confidently distinguish between these two possibilities.
Example
53/udp    open|filtered    domain

## Evidence

refer to screenshot folder

## Status

Pending.

