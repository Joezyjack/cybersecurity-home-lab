
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
2. What does `-sV` do?
3. Why is version information important?
4. Does an identified version automatically prove a vulnerability?

## Evidence

Save the Nmap output.

## Status

Pending.

