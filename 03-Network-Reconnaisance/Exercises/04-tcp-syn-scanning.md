
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
sudo nmap -sS -p 1-1000 <AUTHORIZED_TARGET_IP>
```

## Step 2: Save Results

```bash
sudo nmap -sS -p 1-1000 <AUTHORIZED_TARGET_IP> -oN tcp-syn.txt
```

## Step 3: Compare Results

Compare your SYN scan with the TCP connect scan from Exercise 03.

## Questions

1. What is a SYN packet?
2. Explain the TCP three-way handshake.
3. What does `-sS` mean?
4. How does SYN scanning differ from TCP connect scanning?

## Evidence

Save scan screenshots and your comparison.

## Status

Pending.

