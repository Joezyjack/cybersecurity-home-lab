
# Exercise 02: Lab Device Discovery

## Objective

Identify devices connected to an authorized local network using Netdiscover.

## Explanation

Netdiscover is a network discovery tool that uses ARP requests to identify devices on local IPv4 networks.

It can display IP addresses, MAC addresses and hardware vendor information where available.

## Step 1: Check Installation

```bash
netdiscover -h
```

## Step 2: Start Discovery

```bash
sudo netdiscover
```

Alternatively:

```bash
sudo netdiscover -r <AUTHORIZED_SUBNET_CIDR>
```

## Step 3: Record Results

| IP Address | MAC Address | Device | Vendor |
|---|---|---|---|
| [Insert] | [Insert] | [Insert] | [Insert] |

## Step 4: Compare with Nmap

Compare your Netdiscover results with Exercise 01.

## Questions

1. What is ARP?
2. What is a MAC address?
3. How does Netdiscover identify devices?
4. Why might Nmap and Netdiscover produce different results?

## Evidence

Save a screenshot of the discovery results.

## Status

Previously practised. Refresh evidence and verify current results.

