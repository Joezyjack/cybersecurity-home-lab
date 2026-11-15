
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
