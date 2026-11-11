Exercise 07: Network Reconnaissance Using Nmap

1. Introduction

Nmap (Network Mapper) is an open-source network discovery and security auditing tool.

It is used by network administrators and cybersecurity professionals to identify hosts, examine network ports and investigate available services.

In this exercise, I verified Nmap installation and performed network scans against my own Kali Linux machine.

2. Objectives

* Verify Nmap installation.
* Understand basic Nmap scanning.
* Perform a localhost scan.
* Interpret open, closed and filtered ports.
* Perform service version detection.
* Scan all TCP ports on the local machine.
* Document network reconnaissance findings.

3. Laboratory Environment

Component	Configuration
Operating system	Kali Linux
Tool	Nmap
Version	7.99
Target	127.0.0.1
Target type	Localhost

4. Verify Nmap Installation

Command:

nmap --version

Observed result:

Nmap version 7.99 was successfully displayed.

This confirmed that Nmap was installed and available in the Kali Linux terminal.

5. First Localhost Scan

Command:

nmap 127.0.0.1

Observed results

* Host was up.
* 1,000 default TCP ports were scanned.
* All 1,000 ports were closed.
* No open ports were discovered.

Interpretation

The localhost machine responded to the scan, but none of the 1,000 scanned TCP ports had a service accepting connections.

6. Service Version Detection

Command:

nmap -sV 127.0.0.1

The -sV option instructs Nmap to attempt to identify services and their versions on discovered open ports.

Observed result

* Scan completed successfully.
* Host was up.
* 1,000 ports were closed.
* No service versions were identified.

This was consistent with the absence of open ports in the default scan.

7. Full TCP Port Scan

Command:

nmap -p- 127.0.0.1

The -p- option scans TCP ports from 1 through 65535.

Observed results

* Host was up.
* 65,535 TCP ports were scanned.
* All 65,535 ports were closed.
* No open TCP ports were identified.

8. Understanding Nmap Port States

Open

A service is listening and accepting connections on the port.

Closed

The target responds, but no application is listening on the port.

Filtered

Nmap cannot determine whether the port is open or closed because packet filtering prevents a clear response.

9. Findings

The localhost scan identified the Kali Linux machine as available.

The default scan reported all 1,000 TCP ports closed.

The service version detection scan did not identify any running services among the scanned ports.

The full TCP scan reported all 65,535 TCP ports closed.

10. Security Significance

Network reconnaissance helps security professionals understand the services exposed by a system.

Unnecessary listening services can create additional attack opportunities.

Regular network inspection and service management help reduce unnecessary exposure.

11. Learning Outcomes

Through this exercise, I learned how to:

* Verify Nmap installation.
* Scan a local machine.
* Identify TCP port states.
* Understand service version detection.
* Perform a full TCP port scan.
* Interpret Nmap output.
* Document reconnaissance findings.

12. Limitations

The scans were performed against localhost and focused on TCP ports.

They did not constitute a complete security assessment.

UDP scanning, vulnerability detection, configuration review and testing of other authorized systems were not covered by these results.

13. Conclusion

The Nmap reconnaissance exercise was completed successfully against the local Kali Linux machine.

No open TCP ports were identified in either the default 1,000-port scan or the full TCP port scan.

This exercise provided a foundation for more advanced network discovery and service enumeration.

Platform: Kali Linux
Tool: Nmap 7.99
Module: Networking Fundamentals
Exercise: Localhost Network Reconnaissance
