
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
nmap -sn <192.168.100.0/24>
```

The `-sn` option performs host discovery without a port scan.

## Step 3: Save Results

```bash
nmap -sn <192.168.100.0/24> -oN host-discovery.txt
```

## Step 4: Review Results

Record:

- Number of active hosts 4
- IP addresses discovered 4
- MAC addresses, if shown 4
- Device information, if available

## Questions

1. What is host discovery?
Host discovery is the process of identifying devices (hosts) that are active and reachable on a network.
It helps a network administrator or security analyst determine which devices are currently connected, such as computers, phones, routers, servers, and printers.

2. What does the `-sn` option do?
The Nmap -sn option performs a host discovery scan (Ping Scan) without performing a port scan.
It checks which hosts are alive or responding on the network.
Example:
nmap -sn 192.168.100.0/24

3. Why should you identify the correct subnet before scanning?
Identifying the correct subnet ensures that you scan the intended network and its devices.
It helps you:
- Avoid scanning the wrong network.
- Prevent unnecessary network traffic.
- Stay within your authorized scope.
- Identify the correct range of IP addresses.
- Improve the accuracy of your network discovery.
Always verify your subnet before scanning.

4. What information can Nmap reveal about active devices?
Nmap host discovery can reveal:
- IP address — the device's network address.
- Host status — whether the device appears up or reachable.
- MAC address — sometimes available for local Ethernet discoveries.
- MAC vendor — sometimes inferred from the MAC address.
- Hostname — sometimes discovered through DNS or other resolution methods.
- Network presence — which devices appear active within the scanned range.
Host discovery helps you answer: "Which devices are currently alive on my network?"


## Evidence

check the screenshot folder:

- The command used
- The Nmap output
- The discovered hosts

## Result

Status: [Not Started / In Progress / Completed]

Actual findings: [Insert your results]

