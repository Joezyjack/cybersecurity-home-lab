
# Exercise 04: TCP SYN Scanning

## Objective

Understand and perform a TCP SYN scan against an authorized lab target.

## Explanation

A SYN scan examines responses to TCP connection initiation packets.

It is commonly called a half-open scan because it does not complete the normal TCP connection handshake.

## TCP Three-Way Handshake

1. SYN: Client requests a connection.
2. SYN-ACK: Server acknowledges the request.
3. ACK: Client completes the handshake.

## Step 1: Run SYN Scan

```bash
sudo nmap -sS -p 1-1000 <192.168.100.0/24>
```

## Step 2: Save Results

```bash
sudo nmap -sS -p 1-1000 <192.168.100.0/24> -oN tcp-syn.txt
```

## Step 3: Compare Results

Compare your SYN scan with the TCP connect scan from Exercise 03.

## Questions

1. What is a SYN packet?
A SYN (Synchronize) packet is a TCP packet used to initiate a connection between two devices.
It is the first packet sent when establishing a new TCP connection. It requests that the other device synchronize connection parameters and begin communication.

2. Explain the TCP three-way handshake.
The TCP three-way handshake is the three-step process used to establish a reliable TCP connection between a client and a server.
i. SYN
Client → Server
The client requests to establish a connection.


ii. SYN-ACK
Server → Client
The server acknowledges the request and agrees to establish the connection.


iii. ACK
Client → Server
The client acknowledges the server's response. The connection is established.


SYN → SYN-ACK → ACK = TCP connection established.

3. What does `-sS` mean?
-sS tells Nmap to perform a TCP SYN Scan, also called a Half-Open Scan or Stealth Scan.
Instead of completing the full TCP handshake, Nmap sends a SYN packet and examines the response.
- SYN-ACK → port is likely open
- RST → port is closed
- No response or certain ICMP errors → may be filtered
The S stands for SYN Scan.

4. How does SYN scanning differ from TCP connect scanning?
Feature	TCP Connect (-sT)	SYN Scan (-sS)
Connection	Completes full TCP handshake	Usually doesn't complete handshake
Packets	SYN → SYN-ACK → ACK	SYN → response → scan may terminate
Method	OS completes connection	Nmap handles probe responses
Speed	Can be slower	Often faster
Privileges	Usually no raw packet privileges required	Typically requires root/sudo
Detection	More likely to be logged as a completed connection	May be less visible to application logs, but still detectable
Nmap use	Reliable connection-based check	Efficient port-state discovery
Easy way to remember
- -sT = Talk to the port and complete the connection.
- -sS = Knock on the port, check its response, and usually leave before completing the connection.

## Evidence

Refer to screenshots folder.

## Status

Pending.

