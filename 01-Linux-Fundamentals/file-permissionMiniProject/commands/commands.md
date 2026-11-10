Linux Commands and Implementation Guide

Project: Secure Office File Management System

Operating System: Kali Linux
Project Category: Linux Administration and Cybersecurity
Purpose: User management, group management, file ownership and access control.

⸻

1. Introduction

This document contains the Linux terminal commands used to implement the Secure Office File Management System.

The commands are organized according to the stages of project implementation.

Each command includes a brief explanation of its purpose and its application in the project.

2. Directory Creation

Create the main project directory

mkdir -p ~/Secure-Office
cd ~/Secure-Office

Explanation:

* mkdir creates a directory.
* -p creates parent directories when necessary.
* cd changes the current working directory.

Create departmental directories

mkdir Administration IT Public Shared

Explanation:

Creates four directories representing the organization’s departments.

Verify directory structure

tree

Displays the directory structure and its contents.

3. File Creation

Create departmental files:

touch Administration/employee-records.txt
touch IT/backup.sh
touch IT/technical-note.txt
touch Public/announcements.txt
touch Shared/company-guidelines.txt

Explanation:

The touch command creates empty files when they do not already exist.

Add sample information

echo "Confidential Employee Records" > Administration/employee-records.txt
echo "#!/bin/bash" > IT/backup.sh
echo "echo Backup process started" >> IT/backup.sh
echo "IT Department Technical Documentation" > IT/technical-note.txt
echo "Welcome to our company" > Public/announcements.txt
echo "Company Information Security Guidelines" > Shared/company-guidelines.txt

Explanation:

* echo outputs text.
* > writes text and replaces existing contents.
* >> appends text without removing existing contents.

4. User and Group Management

Create departmental groups

sudo groupadd administration
sudo groupadd itdepartment
sudo groupadd generalstaff

Explanation:

The groupadd command creates Linux groups.

The groups represent the three departments in the organization.

Create departmental user accounts

sudo useradd -m -s /bin/bash adminstaff
sudo useradd -m -s /bin/bash itstaff

For the general staff account, the group was created separately, so use:

sudo useradd -m -s /bin/bash -g generalstaff generalstaff

Explanation:

* useradd creates a user.
* -m creates the user’s home directory.
* -s /bin/bash assigns Bash as the login shell.
* -g assigns an existing primary group.

Set user passwords

sudo passwd adminstaff
sudo passwd itstaff
sudo passwd generalstaff

The passwd command sets or changes account passwords.

Verify user accounts

getent passwd adminstaff
getent passwd itstaff
getent passwd generalstaff

Verify group accounts

getent group administration
getent group itdepartment
getent group generalstaff

Inspect user IDs and group memberships

id adminstaff
id itstaff
id generalstaff

The id command displays user IDs, primary groups and supplementary group memberships.

5. Ownership Management

Ownership determines which user and group are associated with a file or directory.

Administration ownership

sudo chown -R adminstaff:administration Administration

Assigns ownership of the Administration directory and its contents to adminstaff and the administration group.

IT ownership

sudo chown -R itstaff:itdepartment IT

Assigns ownership to the IT user and group.

Public ownership

sudo chown -R generalstaff:generalstaff Public

Assigns ownership to the general staff user and group.

Shared ownership

sudo chown -R root:generalstaff Shared

Assigns ownership to the root user and generalstaff group.

Verify ownership

ls -ld Administration IT Public Shared

For detailed ownership information:

sudo ls -lR Administration IT Public Shared

6. File Permission Management

The chmod command changes file and directory permissions.

Linux uses three basic permission types:

Permission	Numeric value	Description
Read (r)	4	Read file contents
Write (w)	2	Modify file contents
Execute (x)	1	Execute a file or traverse a directory

Administration permissions

sudo chmod 700 Administration
sudo chmod 600 Administration/employee-records.txt

* 700: Only the owner has read, write and execute access to the directory.
* 600: Only the owner can read and modify the employee records file.

IT permissions

sudo chmod 750 IT
sudo chmod 750 IT/backup.sh
sudo chmod 640 IT/technical-note.txt

* 750: Owner has full access; group has read and execute access.
* 640: Owner has read/write access; group has read-only access.

Public permissions

sudo chmod 755 Public
sudo chmod 644 Public/announcements.txt

* 755: Owner has full directory access; group and others have read and execute access.
* 644: Owner can read and modify the file; others can only read it.

Shared permissions

sudo chmod 2770 Shared
sudo chmod 660 Shared/company-guidelines.txt

* 2770: Sets SGID and grants full directory access to the owner and group.
* 660: Allows owner and group to read and modify the file.

Verify permissions

ls -ld Administration IT Public Shared

Inspect individual files:

sudo ls -lR Administration IT Public Shared

Inspect detailed metadata:

sudo stat Administration/employee-records.txt
sudo stat IT/backup.sh
sudo stat Public/announcements.txt
sudo stat Shared/company-guidelines.txt

7. Access-Control Verification

The following commands help verify the departmental accounts.

Check account identities:

id adminstaff
id itstaff
id generalstaff

Switch to the general staff account:

su - generalstaff

Test access to a public announcement using the actual absolute path to the project:

cat /home/YOUR_USERNAME/cybersecurity-home-lab/Secure-Office-File-Management-System/Secure-Office/Public/announcements.txt

Replace YOUR_USERNAME with your original Kali username.

Test access to confidential records:

cat /home/YOUR_USERNAME/cybersecurity-home-lab/Secure-Office-File-Management-System/Secure-Office/Administration/employee-records.txt

Under the intended permissions, an ordinary general staff account should be denied access to the confidential records.

Exit the account:

exit

Note: These tests also depend on the permissions of parent directories. If a parent directory blocks traversal, adjust the lab’s parent-directory access carefully without exposing unrelated private files.

8. File and Directory Inspection

Display the complete project structure:

sudo tree

List directory permissions:

ls -ld Administration IT Public Shared

Inspect file ownership and permissions:

sudo ls -lR Administration IT Public Shared

Inspect individual file metadata:

sudo stat Administration/employee-records.txt

9. Security Audit Commands

Check regular files with the others-write permission:

find . -type f -perm -0002 -ls

Find regular files with permissions exactly 777:

find . -type f -perm 0777 -ls

Find files with SUID enabled:

find . -type f -perm -4000 -ls

These searches examine the current project directory, not the entire operating system.

10. Troubleshooting Commands

Check the current user

whoami

Check current user and groups

id

Check whether a user exists

getent passwd generalstaff

Check whether a group exists

getent group generalstaff

Check whether a file exists

ls -l IT/

Inspect ownership with administrative privileges

sudo ls -l IT/

Rename a file

If the file is named technical-note.txt but the project documentation expects technical-notes.txt:

sudo mv IT/technical-note.txt IT/technical-notes.txt

Apply the permission to the resulting filename:

sudo chmod 640 IT/technical-notes.txt

11. Conclusion

The commands documented in this file demonstrate the practical use of Linux user administration, group management, ownership configuration and access-control permissions.

They provide a reference for reproducing the project and understanding the security purpose of each operation.

All commands should be executed in an authorized laboratory environment and verified against their actual results.

Project: Secure Office File Management System
Platform: Kali Linux
Module: Linux Fundamentals — File Permissions and Ownership
