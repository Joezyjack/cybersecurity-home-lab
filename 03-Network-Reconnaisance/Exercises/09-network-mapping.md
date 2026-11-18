
# Exercise 09: Network Mapping

## Objective

Create a basic network map using information collected during reconnaissance.

## Explanation

Network mapping represents devices and their relationships within a network.

It helps administrators understand network structure and device connectivity.

## Step 1: Collect Network Information

```bash
ip -br addr
```

```bash
ip route
```

## Step 2: Discover Active Hosts

```bash
nmap -sn <AUTHORIZED_SUBNET_CIDR>
```

## Step 3: Discover Device Information

```bash
sudo netdiscover -r <AUTHORIZED_SUBNET_CIDR>
```

## Step 4: Prepare Device Inventory

| Device | IP Address | MAC Address | Role |
|---|---|---|---|
| Kali Linux | [192.168.100.2] | [00:90:4a:31:gy] | Security testing |
| Router | [192.168.100.1] | [00:90:4a:31:61] | 192.168.100.1 |
| iPhone | [192.168.100.35] | [00:90:4a:31:xx] | Mobile device |
| Other | [192.168.100.40] | [00:90:4a:31:xy] | [smartwitch] |

## Step 5: Draw the Network

Example only:

```text
                 Internet
                    |
                  Router
                    |
          -------------------
          |        |        |
        Kali     Phone    Laptop
```

## Questions

1. What is network mapping?
Network mapping is the process of visually or logically representing devices on a network and showing how they are connected or communicate with one another.
It helps a security analyst understand the network structure, identify devices, and see how the network is organized.

2. Why is a device inventory important?
  A device inventory is a record of devices connected to or managed within a network.

    It is important because it helps:
    - Identify authorized and unknown devices.
    - Keep track of network assets.
    - Detect rogue or unauthorized devices.
    - Know which devices need updates.
    - Improve troubleshooting and security monitoring.

3. What information should a network map contain?
        A useful network map may contain:
        Information      |  	Description
        Device name      |   	Name or hostname of the device
        IP address	      |    Logical network address
        MAC address	      |    Hardware/network interface address
        Device type	      |    Router, PC, phone, server, printer, etc.
        Connection	      |    How the device connects to the network
        Network segment    |  	VLAN or subnet where it belongs
        Services	        |    Important exposed services or ports, where relevant

4. How does network segmentation improve security?
    It improves security by:
    - Limiting unauthorized access between segments.
    - Reducing the spread of malware.
    - Isolating sensitive systems.
    - Restricting access to critical devices.
    - Reducing the impact of a compromised device.
    For example, separating guest Wi-Fi from office computers prevents guest devices from having unrestricted access to internal systems.


## Evidence

<img width="1003" height="632" alt="image" src="https://github.com/user-attachments/assets/cf8dfc65-5007-4200-a77d-c054c1245861" />


## Status

Pending.

