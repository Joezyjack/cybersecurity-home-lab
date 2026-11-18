
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
NSE (Nmap Scripting Engine) is a feature of Nmap that uses scripts to automate network discovery, service analysis, security checks, and information gathering.
It helps Nmap perform tasks beyond basic port scanning.

2. What does `-sC` do?
The -sC option runs Nmap's default script set (equivalent to --script=default).
These scripts can help gather additional information about discovered services, such as service details and configurations.
Example:
nmap -sC TARGET_IP

3. Why should scripts be reviewed before execution?
Scripts should be reviewed to understand what they do before running them.
This helps you:
- Know what network requests they send.
- Understand what information they collect.
- Identify potentially intrusive actions.
- Avoid unexpected changes or disruptions.
- Ensure the script is appropriate for your authorized testing scope.

4. Why should intrusive scripts be avoided on uncontrolled systems?
Intrusive scripts may trigger unintended consequences, such as:
- Disrupting services.
- Causing system instability.
- Triggering security alarms.
- Locking accounts.
- Modifying data or system behavior.
- Violating authorization or usage policies.
You should only run intrusive tests in systems you own or have explicit permission to test.

## Evidence

Save terminal screenshots.

## Status

Pending.

