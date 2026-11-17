
# Exercise 01: Host Discovery

## Objective

Identify active devices on an authorized local network using Nmap.

## What Is Host Discovery?

Host discovery is the process of identifying systems that are active and reachable on a network.

It helps a security professional understand which devices are present before conducting further authorized assessments.

## Step 1: Identify Your Network

Run:

```bash
ip -br addr
```

Then:

```bash
ip route
```

Record:

- Network interface
- Current IP address
- Subnet prefix
- Default gateway

Do not assume that a previously used subnet is still current.

## Step 2: Perform Host Discovery

Use the verified subnet:

```bash
nmap -sn <AUTHORIZED_SUBNET_CIDR>
```

The `-sn` option performs host discovery without a port scan.

## Step 3: Save Results

```bash
nmap -sn <AUTHORIZED_SUBNET_CIDR> -oN host-discovery.txt
```

## Step 4: Review Results

Record:

- Number of active hosts
- IP addresses discovered
- MAC addresses, if shown
- Device information, if available

## Questions

1. What is host discovery?
2. What does the `-sn` option do?
3. Why should you identify the correct subnet before scanning?
4. What information can Nmap reveal about active devices?

## Evidence

Save a screenshot showing:

- The command used
- The Nmap output
- The discovered hosts

## Result

Status: [Not Started / In Progress / Completed]

Actual findings: [Insert your results]

