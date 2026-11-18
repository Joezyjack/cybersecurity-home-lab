
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
| [192.168.100.2] | [xx:xx:xx:xx] | [iphone] | [Apple] |

## Step 4: Compare with Nmap

Compare your Netdiscover results with Exercise 01.

## Questions

1. What is ARP?
ARP (Address Resolution Protocol) is a protocol used to discover the MAC address associated with an IPv4 address on a local network.
It helps a device determine which device owns a particular IP address so it can deliver data over the local network.
Example: Your computer wants to send data to 192.168.100.1. ARP helps it discover the MAC address of that device.

2. What is a MAC address?
A MAC (Media Access Control) address is a hardware-level network address used to identify a network interface on a local network.

Example:
AA:BB:CC:11:22:33
- IP address = logical network address.
- MAC address = link-layer address used for local network communication.

3. How does Netdiscover identify devices?
Netdiscover is a network discovery tool that identifies devices on a local network using ARP requests.

It sends ARP requests asking which devices have particular IP addresses. Devices that respond reveal information such as:
- IP address
- MAC address
- MAC vendor (when identifiable)
Netdiscover is particularly useful for discovering devices on a local IPv4 network.

4. Why might Nmap and Netdiscover produce different results?
Because they use different discovery techniques and protocols.
Nmap	          |      Netdiscover
Uses multiple host discovery methods depending on scan options	     |   Primarily uses ARP discovery on local networks
Can discover hosts across different network conditions	            |       Best suited to local Layer 2 networks
Can use ICMP, TCP, UDP and ARP probes	Relies on ARP requests and replies
May discover hosts that respond to its selected probes	May discover devices that respond to ARP

Devices may also be missed because:
- Firewalls block probes.
- Devices are sleeping or disconnected.
- Wi-Fi clients use isolation.
- Devices don't respond to certain discovery methods.
- Scans were performed at different times.


## Evidence

check screenshot folder.

## Status

Previously practised. Refresh evidence and verify current results.

