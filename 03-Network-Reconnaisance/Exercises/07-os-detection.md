# Exercise 07: Operating System Detection

## Objective

Attempt to identify the operating system of an authorized lab target.

## Explanation

Nmap OS detection examines network responses and TCP/IP characteristics to estimate the operating system of a target.

## Step 1: Run OS Detection

```bash
sudo nmap -O <AUTHORIZED_TARGET_IP>
```

## Step 2: Record Results

- Detected operating system:
- Device type:
- OS details:
- Confidence level:

## Limitations

Detection may be affected by:

- Firewalls.
- Network filtering.
- Limited responses.
- Virtualization.
- Similar network implementations.

## Questions

1. What is OS detection?
OS (Operating System) Detection is the process of identifying or estimating the operating system running on a target device, such as Windows, Linux, or macOS.
It helps a security analyst understand what type of system they are examining.

2. What does `-O` do?
The Nmap -O option enables operating system detection.
Nmap analyzes network responses and TCP/IP characteristics to estimate the target's operating system.
Example:
sudo nmap -O 192.168.1.10
The sudo is typically required because OS detection uses raw packet techniques that require elevated privileges.

3. Why might Nmap fail to identify an operating system?
Nmap may fail to identify the OS because:
- The target does not respond to the required probes.
- A firewall blocks or modifies network responses.
- The target is behind a NAT or proxy.
- The target uses unusual or customized network settings.
- Nmap doesn't have enough information to compare responses accurately.
- The target's TCP/IP behavior resembles that of several operating systems.

4. Why should results be treated as estimates?
Nmap does not directly access the target's operating system. It analyzes network behavior and compares it with known fingerprints.
Therefore, its result is an educated inference, not absolute proof.
For example, Nmap may report:
Linux 5.x — 6.x
This suggests the target behaves like systems in that fingerprint range, but it does not confirm the exact Linux version installed.

## Evidence

check screenshot folder.

## Status

Pending.

