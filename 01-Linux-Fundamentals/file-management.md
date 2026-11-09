MODULE 01: LINUX FUNDAMENTALS

MODULE 02: FILE MANAGEMENT

Learning Environment: Kali Linux
Category: Linux System Administration and Cybersecurity
Difficulty: Beginner
Exercise Type: Hands-on Practical Laboratory
Portfolio: Cybersecurity Home Lab

⸻

TABLE OF CONTENTS

1. Introduction
2. Learning Objectives
3. Understanding the Linux Filesystem
4. Understanding File Paths
5. Laboratory Environment Setup
6. Practical Exercises
    * Exercise 1: Listing Files and Directories
    * Exercise 2: Creating Files
    * Exercise 3: Creating Directories
    * Exercise 4: Copying Files and Directories
    * Exercise 5: Moving and Renaming Files
    * Exercise 6: Reading and Inspecting Files
    * Exercise 7: Searching for Files
    * Exercise 8: Identifying File Types and Sizes
    * Exercise 9: Deleting Files and Directories
    * Exercise 10: Practical File Management Challenge
7. Additional Command-Line Skills
8. Practical Assignment
9. Expected Laboratory Results
10. Cybersecurity Applications
11. Security Findings and Analysis
12. Security Best Practices and Remediation
13. Evidence Collection
14. Conclusion and Further Learning

⸻

1. INTRODUCTION

File management is one of the most important foundational skills in Linux system administration.

Linux provides a command-line interface (CLI) through which users can interact with the operating system without depending on graphical applications.

Through the terminal, users can create, organize, copy, move, rename, inspect, search and delete files and directories.

For cybersecurity professionals, these operations are essential because security investigations frequently involve:

* Examining system configuration files.
* Reviewing authentication logs.
* Searching for suspicious files.
* Organizing digital evidence.
* Inspecting file metadata.
* Managing security reports.
* Creating and maintaining backups.
* Investigating potentially malicious scripts.

This laboratory introduces the fundamental Linux file management commands using Kali Linux.

All exercises are designed to be performed inside a dedicated practice directory to prevent accidental modification of important system files.

2. LEARNING OBJECTIVES

At the end of this laboratory, the learner should be able to:

1. Navigate the Linux filesystem using terminal commands.
2. Identify files and directories.
3. Understand absolute and relative paths.
4. Create files and directories.
5. Copy files and directories.
6. Move and rename files.
7. Read and inspect file contents.
8. Search for files using different conditions.
9. Identify file types and metadata.
10. Calculate file and directory sizes.
11. Delete files and directories safely.
12. Organize a structured laboratory environment.
13. Apply basic file management knowledge to cybersecurity investigations.

3. UNDERSTANDING THE LINUX FILESYSTEM

Linux uses a hierarchical filesystem structure.

Unlike Windows, which commonly uses drive letters such as C: and D:, Linux organizes its filesystem from a single starting point called the root directory.

The root directory is represented by:

/

Important Linux directories include:

Directory	Description
/	Root of the entire filesystem
/home	Home directories for regular users
/root	Home directory for the root user
/etc	System configuration files
/var	Variable data, including logs
/tmp	Temporary files
/bin	Essential command binaries
/usr	Applications, libraries and resources
/opt	Optional software packages
/dev	Device files
/mnt	Mount points
/media	Removable storage mount points

Why this matters in cybersecurity

A cybersecurity analyst needs to know where important information is stored.

For example:

* /etc can contain security-related configuration.
* /var/log can contain system and authentication logs.
* /home contains users’ personal files.
* /tmp can contain temporary files that require investigation.

Knowing these locations makes it easier to investigate Linux systems.

4. UNDERSTANDING FILE PATHS

A path identifies the location of a file or directory.

There are two major types.

4.1 Absolute path

An absolute path begins from the root directory /.

Example:

/home/kali/Documents/notes.txt

This identifies the exact location of the file regardless of the current working directory.

4.2 Relative path

A relative path begins from the current working directory.

Example:

documents/notes.txt

This means that the file is inside a directory named documents located within the current directory.

4.3 Special path symbols

Symbol	Meaning
.	Current directory
..	Parent directory
~	Current user’s home directory
/	Root directory

Example:

cd ..

Moves one level backwards to the parent directory.

5. LABORATORY ENVIRONMENT SETUP

Before starting the exercises, create a dedicated working environment.

Open your Kali Linux terminal.

Step 1: Identify your current location

Command:

pwd

Explanation:

The pwd command means Print Working Directory.

It displays the full path of the directory in which the terminal is currently operating.

Step 2: Create the laboratory directory

Command:

mkdir -p ~/cybersecurity-home-lab/01-Linux-Fundamentals/02-File-Management

Explanation:

* mkdir creates directories.
* -p creates missing parent directories.
* ~ represents the current user’s home directory.

Step 3: Enter the laboratory directory

Command:

cd ~/cybersecurity-home-lab/01-Linux-Fundamentals/02-File-Management

Step 4: Confirm your location

Command:

pwd

Expected result:

The output should end with:

cybersecurity-home-lab/01-Linux-Fundamentals/02-File-Management

Step 5: Create practice directories

Commands:

mkdir -p documents backups reports practice

Explanation:

This creates four separate directories.

* documents: Stores sample text files.
* backups: Stores copies of important files.
* reports: Stores report files.
* practice: Stores experimental files and challenge directories.

Verify the structure

Command:

ls -la

If the tree command is available:

tree

Expected structure:

02-File-Management/
├── backups/
├── documents/
├── practice/
└── reports/

⸻

6. PRACTICAL EXERCISES

EXERCISE 1: LISTING FILES AND DIRECTORIES

Objective

To learn how to display files and directories and understand the information provided by Linux directory listings.

Commands and explanations

Task 1: Display directory contents

Command:

ls

Explanation:

Lists the visible files and directories in the current location.

Task 2: Display detailed information

Command:

ls -l

Explanation:

The -l option displays a long listing.

Information includes:

* Permissions.
* Number of hard links.
* Owner.
* Group.
* File size.
* Modification date.
* Filename.

Task 3: Display hidden files

Command:

ls -a

Explanation:

The -a option displays all entries, including hidden files.

In Linux, filenames beginning with a dot are normally hidden from the standard directory listing.

Example:

.bashrc

Task 4: Combine detailed and hidden listings

Command:

ls -la

Explanation:

Combines the functionality of -l and -a.

Task 5: Human-readable file sizes

Command:

ls -lh

Explanation:

Displays file sizes in a format that is easier to understand, such as KB and MB.

Practical activity

Execute all five commands in your laboratory directory.

Observe the differences between the outputs.

Questions

1. What is the difference between ls and ls -la?
2. Why are some Linux files hidden?
3. What information does ls -l provide?
4. What does the -h option do?

Expected learning outcome

The learner should understand how to inspect a directory and identify the information provided by Linux file listings.

⸻

EXERCISE 2: CREATING FILES

Objective

To learn how to create empty files and write information into existing files using the terminal.

Task 1: Create an empty file

Command:

touch documents/notes.txt

Explanation:

The touch command creates an empty file if it does not already exist.

If the file already exists, it normally updates its timestamps rather than replacing its contents.

Task 2: Create additional files

Commands:

touch documents/users.txt

touch documents/network.txt

touch reports/security-report.txt

touch practice/test.txt

Task 3: Verify file creation

Commands:

ls -l documents/

ls -l reports/

ls -l practice/

Explanation:

These commands display the files created in their respective directories.

Task 4: Write information into a file

Command:

echo "Linux File Management Exercise" > documents/notes.txt

Explanation:

The echo command displays text.

The > operator redirects that text into a file.

If the file already contains information, the previous contents are replaced.

Task 5: Append information

Command:

echo "Learning Linux commands with Kali Linux." >> documents/notes.txt

Explanation:

The >> operator appends information to the end of an existing file without removing its previous contents.

Task 6: Read the file

Command:

cat documents/notes.txt

Expected output:

Linux File Management Exercise
Learning Linux commands with Kali Linux.

Important distinction

Operator	Function
>	Creates or overwrites file contents
>>	Appends information

Practical questions

1. What does the touch command do?
2. What happens when you use > on an existing file?
3. How does >> differ from >?
4. Can touch create multiple files in one command?

Try:

touch file1.txt file2.txt file3.txt

⸻

EXERCISE 3: CREATING DIRECTORIES

Objective

To understand directory creation and the organization of files into nested directory structures.

Task 1: Create a directory

Command:

mkdir practice/project1

Explanation:

Creates a directory named project1 inside practice.

Task 2: Create nested directories

Command:

mkdir -p practice/project1/source

Command:

mkdir -p practice/project1/output

Command:

mkdir -p practice/project2/source

Explanation:

The -p option allows multiple directory levels to be created in one operation.

Task 3: Display the structure

Command:

tree

Expected structure:

practice/
├── project1/
│   ├── output/
│   └── source/
└── project2/
    └── source/

If tree is unavailable, install it using:

sudo apt install tree

Task 4: Verify individual directories

Commands:

ls -la practice/

ls -la practice/project1/

Practical questions

1. What is a directory?
2. What is the purpose of mkdir?
3. Why is mkdir -p useful?
4. What is the difference between a file and a directory?

⸻

EXERCISE 4: COPYING FILES AND DIRECTORIES

Objective

To learn how to duplicate files and directory structures without removing the original files.

Task 1: Copy a file

Command:

cp documents/notes.txt backups/

Explanation:

The cp command copies a file from one location to another.

The original file remains in the documents directory.

Task 2: Verify the copied file

Command:

ls -l backups/

Task 3: Copy and rename simultaneously

Command:

cp documents/users.txt backups/users-backup.txt

Explanation:

The destination filename is different from the original filename.

The copied file is now named users-backup.txt.

Task 4: Copy a complete directory

Command:

cp -r practice/project1 backups/

Explanation:

The -r option means recursive.

It allows Linux to copy a directory and its contents, including nested directories.

Task 5: Verify the copied directory

Command:

tree backups/

Practical questions

1. What does cp do?
2. Does copying a file delete the original?
3. Why is -r necessary when copying directories?
4. How can you copy a file and give it a different name?

Cybersecurity application

Copying is important during security investigations because analysts may need to preserve an original file while examining a separate working copy.

⸻

EXERCISE 5: MOVING AND RENAMING FILES

Objective

To understand how to move files between directories and rename files using the Linux terminal.

Task 1: Move a file

Command:

mv documents/network.txt reports/

Explanation:

The mv command moves the file from the documents directory into reports.

Unlike copying, moving normally removes the original directory entry after placing the file at its destination.

Task 2: Rename a file

Command:

mv documents/users.txt documents/user-accounts.txt

Explanation:

The source and destination are in the same directory.

The operation changes the filename.

Task 3: Move and rename simultaneously

Command:

mv reports/security-report.txt reports/linux-security-report.txt

Task 4: Verify the changes

Command:

tree

Expected observations:

* network.txt should no longer be in documents.
* network.txt should be in reports.
* users.txt should now be called user-accounts.txt.
* security-report.txt should now be called linux-security-report.txt.

Practical questions

1. What is the difference between cp and mv?
2. Can mv rename a file?
3. Can mv move a directory?
4. What happens if the destination filename already exists?

Cybersecurity application

Moving and renaming files helps security professionals organize investigation materials and maintain structured evidence directories.

⸻

EXERCISE 6: READING AND INSPECTING FILE CONTENTS

Objective

To learn how to read and inspect file contents using different Linux commands.

Task 1: Display complete contents

Command:

cat documents/notes.txt

Explanation:

Displays the entire contents of the specified file.

Task 2: Read contents interactively

Command:

less documents/notes.txt

Explanation:

Allows users to navigate through a file page by page.

Useful controls:

* Space: Next page.
* b: Previous page.
* /word: Search for a word.
* q: Exit.

Task 3: Display the first 10 lines

Command:

head documents/notes.txt

Explanation:

Displays the beginning of the file.

Task 4: Display the last 10 lines

Command:

tail documents/notes.txt

Explanation:

Displays the end of the file.

Task 5: Count file contents

Command:

wc documents/notes.txt

Explanation:

Displays the number of lines, words and bytes.

Additional commands:

wc -l documents/notes.txt

wc -w documents/notes.txt

wc -c documents/notes.txt

These display line, word and byte counts respectively.

Practical activity

Create a longer text file:

seq 1 30 > documents/numbered-data.txt

Then execute:

head documents/numbered-data.txt

tail documents/numbered-data.txt

head -n 5 documents/numbered-data.txt

tail -n 5 documents/numbered-data.txt

wc -l documents/numbered-data.txt

Expected observation:

The file contains 30 numbered lines.

Cybersecurity application

Reading and inspecting files is essential when examining logs, configuration files and security reports.

For example, an analyst may inspect authentication logs to identify failed login attempts.

⸻

EXERCISE 7: SEARCHING FOR FILES

Objective

To learn how to locate files and directories using the Linux find command.

Task 1: Search for a specific filename

Command:

find . -name "notes.txt"

Explanation:

Searches for a file named notes.txt starting from the current directory.

The dot represents the current directory.

Task 2: Search for all text files

Command:

find . -type f -name "*.txt"

Explanation:

* . identifies the starting location.
* -type f restricts the search to regular files.
* -name "*.txt" matches filenames ending in .txt.

Task 3: Find all directories

Command:

find . -type d

Explanation:

The -type d condition searches for directories.

Task 4: Find files larger than 1 KB

Command:

find . -type f -size +1k

Explanation:

Finds regular files whose size exceeds the specified threshold.

Task 5: Search without considering filename case

Command:

find . -iname "NOTES.TXT"

Explanation:

The -iname option performs a case-insensitive filename search.

Task 6: Search for recently modified files

Command:

find . -type f -mmin -60

Explanation:

Finds regular files modified within the last 60 minutes.

Practical questions

1. What does find do?
2. What does the dot represent?
3. What is the difference between -name and -iname?
4. What is the purpose of -type f?
5. How can you locate files modified within the last hour?

Cybersecurity application

Searching for files is useful when investigating suspicious scripts, identifying unexpected files and locating configuration files.

⸻

EXERCISE 8: IDENTIFYING FILE TYPES AND SIZES

Objective

To understand file identification, metadata inspection and disk usage analysis.

Task 1: Identify file type

Command:

file documents/notes.txt

Explanation:

The file command examines a file and reports its recognized type based on its contents and characteristics.

A filename extension does not necessarily determine the actual file type.

For example, a file called picture.txt may contain image data.

Task 2: Inspect detailed metadata

Command:

stat documents/notes.txt

Explanation:

Displays metadata such as:

* File size.
* Inode number.
* Permissions.
* Ownership.
* Access time.
* Modification time.
* Change time.

Task 3: Check directory size

Command:

du -sh .

Explanation:

* du means disk usage.
* -s summarizes the total.
* -h displays a human-readable size.

Task 4: Check individual directory sizes

Command:

du -sh */

Explanation:

Displays the sizes of the immediate subdirectories.

Task 5: Display filesystem capacity

Command:

df -h

Explanation:

Displays mounted filesystems, available storage and used capacity.

Practical questions

1. What is file metadata?
2. Why is file useful?
3. What information does stat provide?
4. What is the difference between du and df?
5. Why should cybersecurity professionals inspect file metadata?

Cybersecurity application

File metadata can support investigations involving suspicious modifications, file ownership, timestamps and unexpected file types.

Timestamps should be interpreted carefully because they can be altered.

⸻

EXERCISE 9: DELETING FILES AND DIRECTORIES

Objective

To understand how to safely remove files and directories.

Task 1: Create a temporary file

Command:

touch practice/delete-me.txt

Task 2: Delete the file

Command:

rm practice/delete-me.txt

Explanation:

The rm command removes files.

It does not normally send files to a graphical recycle bin.

Task 3: Verify deletion

Command:

ls -la practice/

Task 4: Create an empty directory

Command:

mkdir practice/empty-folder

Task 5: Remove an empty directory

Command:

rmdir practice/empty-folder

Explanation:

The rmdir command removes empty directories.

Task 6: Remove a directory containing files

Command:

mkdir -p practice/removal-test

Command:

touch practice/removal-test/sample.txt

Command:

rm -r practice/removal-test

Explanation:

The -r option allows recursive removal of a directory and its contents.

Security precautions

* Verify the target path before deletion.
* Avoid unnecessary root privileges.
* Never test destructive commands on system directories.
* Be especially careful with wildcards.
* Do not execute unfamiliar recursive deletion commands.

Never use rm -rf / as a learning exercise.

Practical questions

1. What does rm do?
2. What is the difference between rm and rmdir?
3. Why does recursive deletion require caution?
4. Does Linux normally provide a recovery bin for terminal deletion?

⸻

EXERCISE 10: PRACTICAL FILE MANAGEMENT CHALLENGE

Objective

To combine the skills learned in the previous nine exercises.

This challenge should be completed independently, without copying the entire solution.

Challenge requirements

Create a directory named:

file-management-challenge

Inside it, create this structure:

file-management-challenge/
├── personal/
│   ├── profile.txt
│   └── skills.txt
├── system/
│   └── information.txt
├── backups/
└── reports/

Task 1: Create the directory structure

Required command example:

mkdir -p file-management-challenge/personal

Create the remaining directories yourself.

Task 2: Create the required files

Create:

* profile.txt
* skills.txt
* information.txt

Use touch.

Task 3: Write information into the files

Use echo with the appropriate redirection operator.

Suggested content:

Profile:

Name: Cybersecurity Learner

Skills:

Linux Fundamentals, File Management, Network Security

System information:

Operating System: Kali Linux

These are sample training values. Replace them with accurate information if you wish to document your actual environment.

Task 4: Copy a file into backups

Copy profile.txt into the backups directory.

Verify that both copies exist.

Task 5: Rename a file

Rename:

skills.txt

to:

cybersecurity-skills.txt

Task 6: Move a file

Move information.txt into the reports directory.

Task 7: Search for text files

Use find to locate all .txt files within the challenge directory.

Task 8: Read the profile

Display the contents of profile.txt using cat.

Task 9: Inspect storage usage

Use du -sh to determine the total directory size.

Task 10: Verify the final structure

Run:

tree file-management-challenge/

Expected structure:

file-management-challenge/
├── backups/
│   └── profile.txt
├── personal/
│   ├── cybersecurity-skills.txt
│   └── profile.txt
├── reports/
│   └── information.txt
└── system/

The output should match this structure.

⸻

7. ADDITIONAL COMMAND-LINE SKILLS

The following commands extend the knowledge gained from the main exercises.

7.1 Working with wildcards

Wildcards allow commands to match multiple filenames.

Wildcard	Meaning
*	Matches zero or more characters
?	Matches one character
[abc]	Matches one listed character

Examples:

ls *.txt

Lists text files in the current directory.

ls file?.txt

Matches filenames such as file1.txt and fileA.txt.

7.2 Using command history

Command:

history

Displays previously executed shell commands.

This is useful for reviewing previous operations and repeating commands.

7.3 Clearing the terminal

Command:

clear

Clears the visible terminal screen.

7.4 Checking command location

Command:

which ls

Displays the location of the executable used when invoking ls, where available.

7.5 Using tab completion

Begin typing a filename or directory and press the Tab key.

Bash attempts to complete the name automatically.

This reduces typing mistakes and improves command-line efficiency.

⸻

8. PRACTICAL ASSIGNMENT

Assignment title: Linux File Organization and Inspection

Scenario

You have been assigned to organize files belonging to a small cybersecurity investigation.

The files must be separated into evidence, documentation and backup directories.

Assignment tasks

1. Create a main directory named cyber-investigation.
2. Create three subdirectories:
    * evidence
    * documentation
    * backup
3. Create five sample text files inside evidence.
4. Write different sample descriptions into each file.
5. Copy two evidence files into backup.
6. Rename one evidence file.
7. Move one evidence file into documentation.
8. Search for all text files.
9. Inspect the file metadata of one evidence file.
10. Calculate the total directory size.
11. Generate a complete directory listing.
12. Document your observations.

Additional investigation

Create a file named:

documentation/investigation-notes.txt

Write a short report explaining:

* What directories you created.
* What files you created.
* Which files you copied.
* Which file you renamed.
* Which file you moved.
* What you discovered using stat.
* What you learned about safe file management.

Assignment verification

Run:

tree cyber-investigation/

Run:

find cyber-investigation/ -type f

Run:

du -sh cyber-investigation/

Capture screenshots of the actual outputs.

Assessment criteria

Assessment area	Marks
Directory creation	10
File creation	10
File copying	10
Moving and renaming	15
File searching	10
Metadata inspection	10
Storage analysis	10
Documentation	15
Screenshots and evidence	10
Total	100

⸻

9. EXPECTED LABORATORY RESULTS

Upon completing the exercises, the learner should demonstrate the ability to:

* Navigate the Linux filesystem.
* Create organized directory structures.
* Create and edit text files.
* Copy and move files.
* Rename files.
* Search for files using conditions.
* Read and inspect file contents.
* Identify file types.
* Examine metadata.
* Calculate directory sizes.
* Delete temporary files safely.

Actual terminal outputs should be recorded in the laboratory results section.

Do not substitute expected results for actual observations.

⸻

10. CYBERSECURITY APPLICATIONS

Linux file management supports several important cybersecurity activities.

10.1 Security log investigation

Security analysts inspect system logs to investigate authentication attempts and suspicious activities.

Example:

/var/log/auth.log

This file is commonly used for authentication-related logging on Debian-based systems, although the logging configuration may differ.

10.2 Configuration analysis

Security professionals inspect configuration files to understand how services and operating systems are configured.

Example:

/etc/ssh/sshd_config

This file contains OpenSSH server configuration where the SSH server is installed.

10.3 Digital evidence preservation

During incident response, analysts may need to preserve original files and work on separate copies.

Copying and organizing evidence carefully helps reduce accidental modification.

For formal forensic investigations, use approved acquisition and hashing procedures.

10.4 Malware investigation

The file, stat and find commands can assist in identifying and inspecting suspicious files.

Unknown files should be handled in an isolated analysis environment.

10.5 Backup management

Backup directories help organize important information and support recovery processes.

Backups should ideally be maintained separately from the original data and protected from unauthorized modification.

⸻

11. SECURITY FINDINGS AND ANALYSIS

This laboratory focuses on foundational Linux file management.

It does not constitute a vulnerability assessment or penetration test.

The following investigation areas can be explored in subsequent exercises:

Investigation area	What to examine
File ownership	Who owns important files?
File permissions	Who can read, write or execute files?
Hidden files	Are unexpected hidden files present?
File timestamps	When were files accessed or modified?
Configuration files	Are important settings properly protected?
Log files	Are there unusual authentication events?

Findings record

Complete this table using actual observations.

Finding	Actual observation	Recommended action
Directory organization	[Record result]	Maintain structured directories
File metadata	[Record result]	Review unexpected changes
File ownership	[Record result]	Verify appropriate ownership
File permissions	[Record result]	Apply least privilege
Backup verification	[Record result]	Confirm backup integrity

No vulnerability should be reported without sufficient evidence.

⸻

12. SECURITY BEST PRACTICES AND REMEDIATION

1. Use dedicated working directories for experiments.
2. Verify file paths before performing operations.
3. Avoid unnecessary root access.
4. Maintain secure backups.
5. Apply appropriate file permissions.
6. Protect configuration files.
7. Preserve original evidence during investigations.
8. Avoid executing unknown files.
9. Review suspicious file ownership and timestamps.
10. Keep security documentation organized.

Principle of least privilege

The principle of least privilege means giving users and applications only the permissions they need to perform their legitimate tasks.

This concept will be explored practically in the next module on Linux permissions and ownership.

⸻

13. EVIDENCE COLLECTION

Screenshots provide evidence that the exercises were performed.

Recommended screenshot filenames:

screenshots/
├── 01-laboratory-setup.png
├── 02-directory-listing.png
├── 03-file-creation.png
├── 04-directory-creation.png
├── 05-file-copying.png
├── 06-file-moving-renaming.png
├── 07-file-reading.png
├── 08-file-searching.png
├── 09-file-metadata.png
├── 10-file-deletion.png
├── 11-practical-challenge.png
└── 12-final-assignment.png

Evidence requirements

Each screenshot should:

* Show the actual command executed.
* Show the corresponding terminal output.
* Be readable.
* Avoid exposing private information.
* Be saved with a descriptive filename.

⸻

14. CONCLUSION AND FURTHER LEARNING

Linux file management is an essential foundation for anyone pursuing a career in cybersecurity.

Understanding how to create, organize, inspect, search, copy, move and delete files through the terminal improves confidence when working with Linux systems.

These skills provide the foundation for more advanced cybersecurity activities, including system administration, log analysis, digital forensics, vulnerability assessment and penetration testing.

The practical knowledge from this module will be applied in subsequent laboratory exercises.

NEXT MODULE: LINUX FILE PERMISSIONS AND OWNERSHIP

Topics:

1. Understanding Linux file permissions.
2. Reading permission notation.
3. Using chmod.
4. Understanding numeric and symbolic permissions.
5. Changing ownership with chown.
6. Understanding users and groups.
7. Special permissions.
8. Identifying insecure file permissions.
9. Practical security assessment of file access.

⸻

Portfolio: Cybersecurity Home Lab
Module: 01 — Linux Fundamentals
Exercise: 02 — File Management
Platform: Kali Linux
Documentation status: Prepared
Practical execution status: To be completed and verified
Evidence status: To be collected and uploaded

Learning approach: Understand → Execute → Observe → Document → Verify → Publish.
