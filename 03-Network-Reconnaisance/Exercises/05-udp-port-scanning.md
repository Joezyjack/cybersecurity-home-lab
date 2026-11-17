
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
2. How does UDP differ from TCP?
3. Why can UDP scans take longer?
4. Explain open|filtered.

## Evidence

Save the terminal output.

## Status

Pending.

