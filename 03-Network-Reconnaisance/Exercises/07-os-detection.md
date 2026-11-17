
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
2. What does `-O` do?
3. Why might Nmap fail to identify an operating system?
4. Why should results be treated as estimates?

## Evidence

Save the terminal output.

## Status

Pending.

