
# Exercise 08: Nmap Scripting Engine (NSE)

## Objective

Understand how Nmap scripts collect additional information about network services.

## Explanation

The Nmap Scripting Engine allows scripts to automate network discovery, service analysis and other assessment tasks.

NSE script categories include:

- default
- discovery
- safe
- vuln
- intrusive
- brute

Some categories can be disruptive and require additional authorization and care.

## Step 1: Review Default Scripts

```bash
nmap --script-help default
```

## Step 2: Identify Open Ports

Use results from earlier exercises.

## Step 3: Run Default Scripts

```bash
nmap -sC -sV -p <OBSERVED_OPEN_PORTS> <AUTHORIZED_TARGET_IP>
```

## Step 4: Document Results

- Scripts executed:
- Services examined:
- Relevant observations:
- Unexpected output:

## Questions

1. What is NSE?
2. What does `-sC` do?
3. Why should scripts be reviewed before execution?
4. Why should intrusive scripts be avoided on uncontrolled systems?

## Evidence

Save terminal screenshots.

## Status

Pending.

