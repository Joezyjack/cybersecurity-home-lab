
# Security Findings and Remediation

## 1. Linux Account Security

Observation:
The laboratory investigation identified administrative
privileges and account management configurations.

Recommendation:
- Apply least privilege.
- Review unnecessary administrative access.
- Protect privileged sessions.
- Avoid exposing password hashes.

## 2. File Permissions

Observation:
File and directory permissions were investigated
using chmod, chown, chgrp and umask.

Recommendation:
- Avoid unnecessary permissions such as 777.
- Restrict sensitive files.
- Review ownership and group membership.

## 3. Network Exposure

Observation:
The localhost Nmap scans reported all scanned
TCP ports closed.

Recommendation:
- Regularly inspect listening services.
- Disable unnecessary services.
- Perform separate UDP investigations.
- Review firewall configuration.

## 4. Network Discovery

Observation:
Multiple devices were identified on the
authorized local network.

Recommendation:
- Maintain an asset inventory.
- Scan only authorized systems.
- Document exposed services after enumeration.
- Protect network inventory information.

## 5. Assessment Limitations

Host discovery and port scanning alone do not
establish that a system is secure or vulnerable.

Further assessment is required before making
security conclusions.

No confirmed exploitable vulnerability was
identified during these exercises.




OR....,



# Network Security — Remediation Notes

## Introduction

Remediation refers to actions taken to reduce or eliminate identified security weaknesses.

The following recommendations are general defensive measures. Apply them only where the corresponding exposure is confirmed.

## 1. Unnecessary Open Ports

Risk:

Unnecessary open ports may expose services that are not required.

Recommended actions:

- Disable unused services.
- Close unnecessary ports using firewall rules.
- Review listening services regularly.
- Restrict access to administrative services.

## 2. Exposed Remote Access Services

Risk:

Poorly secured remote access services may allow unauthorized access.

Recommended actions:

- Use strong authentication.
- Disable unused remote access services.
- Use SSH keys where appropriate.
- Restrict remote access to trusted networks.
- Keep remote access software updated.

## 3. Outdated Services

Risk:

Outdated services may contain publicly known vulnerabilities.

Recommended actions:

- Update affected software.
- Remove unsupported services.
- Monitor security advisories.
- Apply vendor security patches.

## 4. Unnecessary UDP Services

Risk:

Unnecessary UDP services may increase the network's attack surface.

Recommended actions:

- Disable unused UDP services.
- Restrict UDP traffic using firewall rules.
- Monitor exposed services.

## 5. Poor Network Segmentation

Risk:

Devices on the same unrestricted network may communicate when they do not need to.

Recommended actions:

- Separate guest and trusted networks.
- Use VLANs where supported.
- Restrict communication between sensitive devices.
- Apply appropriate access-control rules.

## 6. General Security Recommendations

- Maintain an updated operating system.
- Use host-based and network firewalls.
- Review device configurations.
- Monitor network activity.
- Maintain an inventory of connected devices.
- Perform authorized security assessments regularly.

## Conclusion

Network security is an ongoing process. Reconnaissance findings should be reviewed, prioritized, and addressed according to the actual risk they present.


