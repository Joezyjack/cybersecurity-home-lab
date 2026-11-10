Project Findings and Security Analysis

1. Introduction

This document records the findings from the Secure Office File Management System project.

The project involved creating departmental Linux users and groups, configuring ownership, applying file permissions and establishing access restrictions.

The objective was to demonstrate basic Linux access control and security hardening.

2. Findings

Finding 1: Departmental User Administration

Observation:

Separate Linux accounts were created for the Administration, IT and General Staff departments.

Commands used:

sudo useradd -m -s /bin/bash adminstaff
sudo useradd -m -s /bin/bash itstaff
sudo useradd -m -s /bin/bash generalstaff

Security significance:

Separate user accounts make it possible to assign permissions according to individual responsibilities instead of sharing one account.

Recommendation:

Each employee should use an individual account with appropriate group membership.

Finding 2: Departmental Group Management

Observation:

Departmental groups were created to organize users according to their responsibilities.

Commands used:

sudo groupadd administration
sudo groupadd itdepartment
sudo groupadd generalstaff

Security significance:

Groups simplify access management when multiple users require similar permissions.

Recommendation:

Review group membership regularly and remove accounts that no longer require access.

Finding 3: Ownership Configuration

Observation:

Ownership was assigned to departmental users and groups.

Commands used:

sudo chown -R adminstaff:administration Administration
sudo chown -R itstaff:itdepartment IT
sudo chown -R generalstaff:generalstaff Public
sudo chown -R root:generalstaff Shared

Security significance:

Ownership determines which user and group are associated with files and directories.

Recommendation:

Ensure that ownership reflects the actual responsibilities of each department.

Finding 4: Confidential File Protection

Observation:

The Administration directory was configured with permission 700, while the employee records file was assigned permission 600.

Commands used:

sudo chmod 700 Administration
sudo chmod 600 Administration/employee-records.txt

Security significance:

These settings restrict ordinary access to confidential employee information.

Recommendation:

Confidential records should only be accessible to authorized personnel.

Finding 5: IT Department Access Control

Observation:

The IT directory was configured with permission 750.

The backup script was assigned permission 750, while technical documentation was assigned permission 640.

Commands used:

sudo chmod 750 IT
sudo chmod 750 IT/backup.sh
sudo chmod 640 IT/technical-notes.txt

Security significance:

This configuration gives the IT owner full access, permits appropriate group access and denies access to others.

Recommendation:

Review executable permissions and ensure scripts are accessible only to authorized users.

Finding 6: Public Information Access

Observation:

The Public directory was assigned permission 755, and announcements were assigned permission 644.

Commands used:

sudo chmod 755 Public
sudo chmod 644 Public/announcements.txt

Security significance:

This allows users to read public information without granting everyone permission to modify it.

Recommendation:

Public information should be readable where necessary but protected against unauthorized modification.

Finding 7: Shared Directory Configuration

Observation:

The Shared directory was assigned permission 2770.

The SGID bit was used to support group inheritance.

Commands used:

sudo chmod 2770 Shared
sudo chmod 660 Shared/company-guidelines.txt

Security significance:

Group members can access the shared directory, while unrelated users are denied ordinary access.

Recommendation:

Review shared directory membership and monitor modifications to shared files.

3. Troubleshooting Findings

During implementation, some command errors occurred.

Issue 1: User Does Not Exist

An attempt to modify the generalstaff account returned:

usermod: user 'generalstaff' does not exist

Cause:

The group existed, but the user account had not yet been created.

Resolution:

The account was created and assigned to the existing group using useradd with the -g option.

Issue 2: Incorrect Filename

An attempt to change the permission of technical-notes.txt returned a file-not-found error because the actual filename was technical-note.txt.

Cause:

The command referenced a filename that did not exactly match the existing file.

Resolution:

The filename was identified and corrected before applying the permission.

Issue 3: Permission Denied While Listing Directories

The normal Kali account could not inspect directories after ownership and permissions were changed.

Cause:

The directories were restricted to their designated owners and groups.

Resolution:

Administrative inspection was performed using sudo.

4. Overall Security Assessment

The project demonstrated how Linux ownership, groups and permissions can establish basic departmental access control.

The configuration illustrates the principle of least privilege.

A complete security assessment should also verify actual access using each departmental account, inspect parent-directory permissions, review sudo privileges and test shared-directory behaviour.

5. Conclusion

This project provided practical experience in Linux user administration, group management, ownership configuration and file permissions.

It also demonstrated the importance of troubleshooting, verification and documenting security configurations.

The knowledge gained provides a foundation for Linux system hardening, vulnerability assessment and further cybersecurity laboratory exercises.
