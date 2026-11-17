
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
2. Why is a device inventory important?
3. What information should a network map contain?
4. How does network segmentation improve security?

## Evidence

Save your completed network diagram.

## Status

Pending.

