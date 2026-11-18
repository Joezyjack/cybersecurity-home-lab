
# Exercise 03: TCP Port Scanning

## Objective

Identify TCP ports that are open, closed or filtered on an authorized lab device.

## Explanation

TCP port scanning helps identify network services that may be accepting connections.

Common TCP ports include:

| Port | Common Service | Purpose |
|---|---|---|
| 21 | FTP | File Transfers |
| 22 | SSH | Remote Access |
| 25 | SMTP | Email Transmission |
| 53 | DNS | Domain Name System |
| 80 | HTTP | Web traffic |
| 443 | HTTPS | Secure web traffic |
| 3306 | MySQL | Database |
| 3389 | RDP |

## Port States

- Open: A service is accepting connections.
- Closed: No service is listening on the port.
- Filtered: Filtering prevents Nmap from determining the port state.

## Step 1: Perform TCP Connect Scan

```bash
nmap -sT -p 1-1000 <192.168.100.0/24>
```

## Step 2: Save Results

```bash
nmap -sT -p 1-1000 <192.168.100.0/24> -oN tcp-connect.txt
```

## Step 3: Document Findings

| Port | State | Service |
|---|---|---|
| 22 | closed | FTP |
| 80 | Open | HTTP |
| 443 | Closed | HTTPS |

## Questions

1. What is a TCP port?
A TCP port is a virtual communication endpoint on a device that allows different applications and services to communicate over a network.

2. What does `-sT` mean?
-sT tells Nmap to perform a TCP Connect Scan.
Nmap attempts to establish a complete TCP connection to the target port using the operating system's connection function.
- If the connection succeeds → Open
- If the connection is refused → Closed
- If a firewall blocks or interferes → Filtered
The T stands for TCP Connect Scan.

3. What is the difference between open and filtered?
Open:	The port is reachable and a service is listening for connections.
Filtered:	Nmap cannot determine whether the port is open because a firewall or network filter is blocking or interfering with its probes.
Example:
- Port 22 open → SSH may be accepting connections.
- Port 22 filtered → A firewall may be preventing Nmap from determining the port's state.
Open = service reachable. Filtered = network filtering prevents a clear answer.

5. Why should unnecessary open ports be investigated?
Every open port may expose a service that could become an entry point for an attacker.
Unnecessary open ports increase the attack surface.

For example, an unused FTP service might:
- Have weak passwords.
- Contain outdated software.
- Have known vulnerabilities.
- Allow unauthorized access.
- Provide an unnecessary pathway into the system.
The security principle is:
If a service is not needed, disable it or restrict access to it.
This is called attack surface reduction.

## Evidence

Refer to the screenshot folder 


Pending.

