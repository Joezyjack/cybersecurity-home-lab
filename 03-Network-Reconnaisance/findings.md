
# Network Reconnaissance — Findings

## Introduction

This document records observations made during network reconnaissance exercises.

The purpose is to identify active devices, network services, open ports, and possible security exposures within an authorized lab environment.

## 1. Host Discovery Findings

Target subnet: [Insert verified subnet]

Tool: Nmap

Command:

```bash
nmap -sn <AUTHORIZED_SUBNET_CIDR>
```

Results:

- Total hosts discovered: 4
- Active hosts: 3
- Network gateway: 182.168.100.1
- Other identified devices: Nil

Observation:

[Describe what the scan revealed.]

## 2. Device Discovery Findings

Tool: Netdiscover

Command:

```bash
sudo netdiscover -r <AUTHORIZED_SUBNET_CIDR>
```

Results:

| IP Address | MAC Address | Identified Device | Observation |
|---|---|---|---|
| [192.168.100.1] | [xx:xx:xx:xx] | [Router] | [Up] |
| [192.168.100.20] | [xx:xx:xx:xx:xx] | [iphone] | [Up] |

## 3. TCP Port Scanning Findings

Target IP: [192.168.100.0/24]

Command:

```bash
nmap -sT -p 1-1000 <192.168.100.0/24>
```

Results:

| Port | State | Service |
|---|---|---|
| [1-1000] | [closed] | [Nil] |

Observation:

[Describe the open, closed, or filtered ports.]

After running python3 to run a window server 8000, the port 8000 became open

## 4. TCP SYN Scan Findings

Command:

```bash
sudo nmap -sS -p 1-1000 <192.168.100.0/24>
```

Observation:

[Compare the SYN scan results with the TCP connect scan.]

## 5. UDP Scan Findings

Command:

```bash
sudo nmap -sU --top-ports 20 <AUTHORIZED_TARGET_IP>
```

Observation:

[Record discovered UDP ports and their states.]

## 6. Service Detection Findings

Command:

```bash
nmap -sV -p <OBSERVED_OPEN_PORTS> <AUTHORIZED_TARGET_IP>
```

Results:

| Port | Service | Version |
|---|---|---|
| [Port] | [Service] | [Version] |

Observation:

[Explain the services identified.]

## 7. Operating System Detection

Command:

```bash
sudo nmap -O <AUTHORIZED_TARGET_IP>
```

Detected operating system: [Insert result]

Confidence: [Insert Nmap confidence if provided]

Observation:

[Explain whether the result was conclusive.]

## 8. Nmap Scripting Engine Findings

Command:

```bash
nmap -sC -sV -p <OBSERVED_OPEN_PORTS> <AUTHORIZED_TARGET_IP>
```

Observation:

[Document scripts executed and relevant output.]

## Conclusion

The reconnaissance exercises provided practical experience in identifying active hosts, discovering network services, and understanding the exposure of systems within an authorized lab environment.

Further analysis and remediation will be based on verified findings.

