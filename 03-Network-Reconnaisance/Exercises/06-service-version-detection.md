
# Exercise 06: Service and Version Detection

## Objective

Identify services and their software versions on discovered open ports.

## Explanation

Service detection helps determine what software is listening on an open network port.

The port number alone does not confirm the actual service.

## Step 1: Identify Open Ports

Use results from previous exercises.

## Step 2: Perform Version Detection

```bash
nmap -sV -p <OBSERVED_OPEN_PORTS> <AUTHORIZED_TARGET_IP>
```

Example format:

```bash
nmap -sV -p 22,80 <AUTHORIZED_TARGET_IP>
```

Use only ports actually discovered on your target.

## Step 3: Document Results

| Port | Service | Version |
|---|---|---|
| [Insert] | [Insert] | [Insert] |

## Questions

1. What is service detection?
Service detection is the process of identifying the services or applications running on open ports of a target device.
For example, discovering that a device has port 22 open and is running SSH, or port 80 running HTTP.

2. What does `-sV` do?
The Nmap option -sV enables service and version detection.
It probes open ports to identify:
- Service name (SSH, HTTP, FTP, etc.)
- Software name
- Software version
- Sometimes additional service details
Example:
nmap -sV 192.168.1.10

3. Why is version information important?
Version information helps security analysts determine whether software is:
- Outdated
- Unsupported
- Affected by known security vulnerabilities
- In need of an update or patch
It also helps administrators plan maintenance and security improvements.

4. Does an identified version automatically prove a vulnerability?
No.

Identifying a software version does not automatically mean the system is vulnerable.
A vulnerability assessment must consider:
- Whether the vulnerability affects that exact version.
- Whether the vulnerable feature or configuration is present.
- Whether the vendor has backported security patches.
- Whether the system is properly configured.
- Whether the vulnerability is actually applicable to that environment.
For example, an application may report an older version number but contain security patches backported by its Linux distribution.


## Evidence

check screenshot on screenshot folder.

## Status

Pending.

