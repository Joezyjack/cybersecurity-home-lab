
# Exercise 03: TCP Port Scanning

## Objective

Identify TCP ports that are open, closed or filtered on an authorized lab device.

## Explanation

TCP port scanning helps identify network services that may be accepting connections.

Common TCP ports include:

| Port | Common Service |
|---|---|
| 21 | FTP |
| 22 | SSH |
| 25 | SMTP |
| 53 | DNS |
| 80 | HTTP |
| 443 | HTTPS |
| 3306 | MySQL |
| 3389 | RDP |

## Port States

- Open: A service is accepting connections.
- Closed: No service is listening on the port.
- Filtered: Filtering prevents Nmap from determining the port state.

## Step 1: Perform TCP Connect Scan

```bash
nmap -sT -p 1-1000 <AUTHORIZED_TARGET_IP>
```

## Step 2: Save Results

```bash
nmap -sT -p 1-1000 <AUTHORIZED_TARGET_IP> -oN tcp-connect.txt
```

## Step 3: Document Findings

| Port | State | Service |
|---|---|---|
| [Insert] | [Insert] | [Insert] |

## Questions

1. What is a TCP port?
2. What does `-sT` mean?
3. What is the difference between open and filtered?
4. Why should unnecessary open ports be investigated?

## Evidence

Save terminal screenshots and scan output.

## Status

Pending.

