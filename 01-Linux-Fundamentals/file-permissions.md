Linux File Permissions – Cybersecurity Home Lab

Module: Linux Fundamentals
Topic: File Permissions and Access Control
Operating System: Kali Linux
Level: Beginner
Status: Practical Learning and Documentation

⸻

1. Introduction

Linux file permissions are an essential component of operating system security. They determine who can access, read, modify, execute, or manage files and directories.

As part of my cybersecurity learning journey, this practical module explores Linux access control mechanisms and how they help protect sensitive information from unauthorized access and modification.

The exercises were performed in a Kali Linux environment using command-line tools.

2. Learning Objectives

By completing this module, I aim to understand and demonstrate how to:

* Interpret Linux file permission structures.
* Identify file owners, groups, and other users.
* Understand read, write, and execute permissions.
* Inspect permissions using ls -l, ls -ld, and stat.
* Modify permissions using chmod.
* Apply numerical and symbolic permission methods.
* Change file ownership using chown.
* Change group ownership using chgrp.
* Understand default permissions using umask.
* Identify SUID, SGID, and Sticky Bit permissions.
* Troubleshoot permission-denied errors.
* Apply the principle of least privilege.

3. Linux Permission Structure

Linux uses three primary permission categories:

Category	Symbol	Description
Owner	u	User who owns the file
Group	g	Users belonging to the file’s group
Others	o	All other users

Three basic permission types control access:

Permission	Symbol	Numeric Value	Description
Read	r	4	Allows reading file contents
Write	w	2	Allows modifying file contents
Execute	x	1	Allows executing a file

Understanding Permission Notation

Example:

-rwxr-xr--

This can be divided into:

* -: Regular file.
* rwx: Owner has read, write, and execute permissions.
* r-x: Group has read and execute permissions.
* r--: Others have read-only permissions.

4. Practical Exercises

Exercise 1: Creating the Laboratory Environment

Create a dedicated directory for the practical activities.

mkdir -p ~/cybersecurity-home-lab/03-file-permissions
cd ~/cybersecurity-home-lab/03-file-permissions

Create sample files:

touch secret.txt public.txt script.sh

Create directories:

mkdir private public

Verify the structure:

ls -la

Exercise 2: Inspecting File Permissions

Use the following commands:

ls -l
ls -la
ls -l secret.txt
ls -ld private

Learning outcome:

Understand how Linux displays file types, permissions, ownership, groups, file sizes, and modification dates.

Exercise 3: Understanding Numerical Permissions

Linux numerical permissions use the following values:

* Read = 4
* Write = 2
* Execute = 1

Examples:

Permission	Numeric Value	Meaning
---	0	No permissions
--x	1	Execute only
-w-	2	Write only
r--	4	Read only
r-x	5	Read and execute
rw-	6	Read and write
rwx	7	Full permissions

Common permission combinations:

Numeric	Owner	Group	Others
777	Full	Full	Full
755	Full	Read/Execute	Read/Execute
750	Full	Read/Execute	None
700	Full	None	None
644	Read/Write	Read	Read
640	Read/Write	Read	None
600	Read/Write	None	None

Exercise 4: Changing Permissions with chmod

Numerical method

chmod 744 secret.txt
chmod 644 public.txt
chmod 700 secret.txt
chmod 600 secret.txt
chmod 000 secret.txt

Restore permissions when necessary:

chmod 600 secret.txt

Symbolic method

Add execute permission to the owner:

chmod u+x script.sh

Remove write permission from others:

chmod o-w public.txt

Add read and write permissions to the group:

chmod g+rw public.txt

Remove all permissions from others:

chmod o-rwx secret.txt

Give everyone read permission:

chmod a+r public.txt

Verify changes:

ls -l

Exercise 5: Directory Permissions

Create and manage directory permissions.

chmod 700 private
chmod 755 public
ls -ld private public

Important directory permission concepts:

* Read: Allows listing directory contents.
* Write: Allows creating, deleting, or renaming entries, subject to other access controls.
* Execute: Allows entering or traversing the directory.

Exercise 6: Changing File Ownership

Identify the current user:

whoami

Display user and group information:

id
groups

Inspect ownership:

ls -l secret.txt

Change ownership to root:

sudo chown root secret.txt

Restore ownership to the Kali user:

sudo chown kali secret.txt

Change owner and group:

sudo chown kali:kali secret.txt

Change ownership recursively:

sudo chown -R kali:kali private

Exercise 7: Changing Group Ownership

Inspect existing groups:

groups

Change the group ownership:

sudo chgrp root secret.txt

Restore the group:

sudo chgrp kali secret.txt

Verify:

ls -l secret.txt

Exercise 8: Understanding umask

Inspect the current umask:

umask

Set a temporary umask:

umask 077

Create a file and directory:

touch private-file.txt
mkdir private-folder

Inspect their permissions:

ls -l private-file.txt
ls -ld private-folder

Restore the common umask setting for the current shell:

umask 022

With the usual default creation modes, umask 022 produces:

* Files: 644
* Directories: 755

Exercise 9: Special Permissions

SUID – Set User ID

Inspect:

ls -l /usr/bin/passwd

SUID allows an executable to run with the effective user privileges of its owner.

SGID – Set Group ID

Apply SGID to a directory:

chmod g+s public

Inspect:

ls -ld public

SGID on a directory causes newly created entries to inherit its group ownership.

Sticky Bit

Inspect the temporary directory:

ls -ld /tmp

Apply the Sticky Bit:

chmod +t public

Verify:

ls -ld public

The Sticky Bit helps prevent ordinary users from deleting or renaming entries owned by other users in shared directories.

Exercise 10: Troubleshooting Permission Errors

Apply restrictive permissions:

chmod 000 secret.txt

Inspect:

ls -l secret.txt

Restore permissions:

chmod 600 secret.txt

The exercise demonstrates how permission restrictions affect access and why correct permission management is important.

5. Cybersecurity Practical Scenarios

Scenario 1: Protecting Confidential Information

A company stores sensitive employee records on a Linux server.

Recommended permission:

chmod 600 salary-records.txt

This restricts normal file access to the owner.

Scenario 2: Protecting Executable Scripts

A backup script should be executable by other users but modifiable only by its owner.

Recommended permission:

chmod 755 backup.sh

Scenario 3: Securing Private Directories

A directory contains confidential company information.

Recommended permission:

chmod 700 confidential

Scenario 4: Investigating Excessive Permissions

A suspicious script is discovered with:

-rwxrwxrwx

This represents permission 777.

Security concerns include:

* Unauthorized modification.
* Potential malicious code injection.
* Unauthorized execution.
* Increased risk of privilege abuse.

A safer permission should be selected based on the actual operational requirements.

6. Assignments

Assignment 1: Basic Knowledge

1. Explain read, write, and execute permissions.
2. Differentiate between Owner, Group, and Others.
3. Explain -rwxr-xr--.
4. What does chmod 755 accomplish?
5. Explain the difference between chmod and chown.
6. What is the purpose of chgrp?
7. Explain the function of umask.

Assignment 2: Practical Configuration

Create the following directory structure:

permissions-assignment/
├── confidential/
├── scripts/
├── public/
├── password.txt
├── report.txt
└── backup.sh

Apply these permissions:

Resource	Required Permission
confidential/	700
scripts/	750
public/	755
password.txt	600
report.txt	644
backup.sh	750

Change the ownership of report.txt to root, then restore it to your Kali user.

Verify all configurations using:

ls -la
stat report.txt

Assignment 3: Cybersecurity Challenge

Assume you are responsible for securing a Linux server.

Configure the following resources:

Resource	Security Requirement
company-secrets.txt	Owner only
staff-records.txt	Owner and group read/write
company-policy.txt	Everyone can read; owner can modify
admin-script.sh	Owner can modify and execute; group can execute
shared-folder/	Owner full access; group read and enter

For each resource:

1. Create the file or directory.
2. Apply the appropriate permissions.
3. Verify the configuration.
4. Explain why you selected those permissions.
5. Discuss the security implications of excessive permissions.

7. Important Commands Reference

Command	Purpose
ls -l	Display file permissions
ls -la	Display all files and permissions
ls -ld	Display directory permissions
chmod	Change permissions
chown	Change ownership
chgrp	Change group ownership
umask	Configure default permission mask
whoami	Identify current user
id	Display user and group IDs
groups	Display group memberships
stat	Display detailed file information
getfacl	Display access control lists
setfacl	Modify access control lists

8. Key Cybersecurity Lessons

During this module, the following security principles were explored:

1. Apply the principle of least privilege.
2. Avoid granting unnecessary permissions.
3. Protect confidential information through restrictive access controls.
4. Understand ownership before modifying permissions.
5. Avoid unnecessary root privileges.
6. Verify permission changes after executing commands.
7. Understand special permissions because they can affect system security.

9. Evidence and Documentation

Practical evidence should include screenshots showing:

* File permission inspection using ls -l.
* Numerical permission changes using chmod.
* Symbolic permission changes.
* File ownership and group modifications.
* Umask configuration.
* SUID, SGID, and Sticky Bit examples.
* Completed practical assignments.

Screenshots should be saved in the module’s screenshots/ directory.

10. Conclusion

Linux file permissions are fundamental to operating system security and administration.

This module provides practical experience in managing file access, controlling ownership, configuring default permissions, and understanding special permission mechanisms.

These skills provide an important foundation for further cybersecurity studies, particularly Linux system administration, server hardening, access control, vulnerability assessment, and penetration testing.

⸻

Repository: cybersecurity-home-lab
Module: Linux Fundamentals – File Permissions
Platform: Kali Linux
Learning Focus: Linux Security and Access Control
