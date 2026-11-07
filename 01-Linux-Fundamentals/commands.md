# Linux Fundamentals – System Identification

## 1. Introduction

Linux is an open-source operating system widely used in cybersecurity, system administration, cloud computing, networking and software development.

Kali Linux is a Debian-based Linux distribution designed primarily for penetration testing, digital forensics, security auditing and cybersecurity research.

Understanding Linux fundamentals is essential for cybersecurity professionals because many security tools, servers, network services and penetration-testing environments operate on Linux.

This practical exercise introduces basic Linux commands used to identify the current user, computer hostname, working directory, operating system, kernel version, system architecture and uptime.

## 2. Lab Information

| Item | Description |
|---|---|
| Module | 01 – Linux Fundamentals |
| Exercise | 01 – System Identification |
| Operating System | Kali Linux |
| Environment | Kali Linux Live with Persistence |
| Interface | Linux Terminal |
| Difficulty | Beginner |
| Category | Linux System Administration |
| Purpose | System identification and information gathering |

## 3. Learning Objectives

At the end of this exercise, I aimed to understand how to:

1. Identify the currently logged-in Linux user.
2. Determine the hostname of a Linux computer.
3. Identify the current working directory.
4. Retrieve operating system information.
5. Identify the running Linux kernel version.
6. Determine the system processor architecture.
7. Check how long the system has been running.

## 4. Practical Exercises and Command Analysis

### Task 1: Identify the Current User

**Command:**

```bash
whoami
```

**Description:**

The `whoami` command displays the username of the account currently executing commands in the terminal.

**Purpose:**

It helps determine which user account is being used to interact with the Linux system.

**Example output:**

```text
kali
```

The output `kali` indicates that the currently logged-in user is named `kali`.

**Cybersecurity relevance:**

User identification is important during security assessments because permissions and access rights depend on the account being used.

It also helps security analysts determine whether commands are being executed under a standard user account or a privileged account.

### Task 2: Identify the System Hostname

**Command:**

```bash
hostname
```

**Description:**

The `hostname` command displays the name assigned to the computer on the network.

**Purpose:**

It helps identify the machine being accessed or administered.

**Example output:**

```text
kali
```

This indicates that the computer's hostname is `kali`.

**Cybersecurity relevance:**

Hostnames help security professionals identify devices during network discovery, system administration and incident investigations.

When several computers are connected to a network, hostnames make it easier to distinguish one system from another.

### Task 3: Identify the Current Working Directory

**Command:**

```bash
pwd
```

**Full meaning:** Print Working Directory.

**Description:**

The `pwd` command displays the absolute path of the directory currently being accessed in the terminal.

**Example output:**

```text
/home/kali
```

This indicates that the current working directory is `/home/kali`.

**Understanding the output:**

- `/` represents the root directory.
- `home` is a directory under the root directory.
- `kali` is the home directory belonging to the Kali user.

**Cybersecurity relevance:**

Understanding the current directory is important when navigating files, locating configuration files, running scripts and analysing system directories.

It also helps prevent accidental file modifications or deletions in the wrong location.

### Task 4: Identify the Operating System

**Command:**

```bash
cat /etc/os-release
```

**Description:**

The `cat` command displays the contents of a file.

The `/etc/os-release` file contains identification information about the installed Linux distribution.

**Purpose:**

This command helps identify the operating system, distribution name, version and related information.

**Example output:**

```text
PRETTY_NAME="Kali GNU/Linux Rolling"
NAME="Kali GNU/Linux"
ID=kali
ID_LIKE=debian
```

The exact output may differ depending on the installed Kali release.

**Understanding the output:**

- `PRETTY_NAME`: Human-readable operating system name.
- `NAME`: Operating system name.
- `ID`: Distribution identifier.
- `ID_LIKE`: Distribution family or compatibility information.

**Cybersecurity relevance:**

Identifying the operating system is an important first step during system enumeration and vulnerability assessment.

Different operating systems and versions may have different security configurations, software packages and vulnerabilities.

### Task 5: Identify the Linux Kernel Version

**Command:**

```bash
uname -r
```

**Description:**

The `uname` command displays system information. The `-r` option displays the kernel release version.

**Example output:**

```text
6.x.x-kali-amd64
```

This is an illustrative example. The actual version depends on the running Kali kernel.

**Understanding the output:**

The kernel is the core component of Linux. It manages communication between hardware and software, memory management, processes and system resources.

**Cybersecurity relevance:**

Kernel identification helps security professionals:

- Check whether a system uses an outdated kernel.
- Research known kernel vulnerabilities.
- Determine compatibility with security tools.
- Investigate kernel-related security updates.

An outdated kernel may expose a system to known security weaknesses.

### Task 6: Identify the System Architecture

**Command:**

```bash
uname -m
```

**Description:**

The `-m` option displays the machine hardware architecture reported by the running kernel.

**Example output:**

```text
x86_64
```

**Understanding the output:**

- `x86_64`: 64-bit x86 architecture.
- `i686`: 32-bit x86 architecture.
- `aarch64`: 64-bit ARM architecture.

**Cybersecurity relevance:**

System architecture is important when selecting compatible software, installing security tools, compiling programs and analysing binary files.

For example, a security tool compiled for ARM may not run natively on an x86_64 system.

### Task 7: Check System Uptime

**Command:**

```bash
uptime
```

**Description:**

The `uptime` command displays how long a Linux system has been running since its last boot.

**Example output:**

```text
07:30:00 up 2 hours, 15 min, 1 user, load average: 0.10, 0.15, 0.12
```

**Understanding the output:**

- `07:30:00`: Current system time.
- `up 2 hours, 15 min`: Time since the system was started.
- `1 user`: Number of logged-in user sessions.
- `load average`: Average system load over the last 1, 5 and 15 minutes.

**Cybersecurity relevance:**

System uptime can help administrators and security analysts understand system availability, identify unexpected restarts and investigate unusual system activity.

It is also useful during troubleshooting and system performance monitoring.

## 5. Summary of Commands Practised

| Command | Function |
|---|---|
| `whoami` | Displays the current username |
| `hostname` | Displays the computer hostname |
| `pwd` | Displays the current working directory |
| `cat /etc/os-release` | Displays operating system information |
| `uname -r` | Displays the kernel release |
| `uname -m` | Displays the system architecture |
| `uptime` | Displays system uptime and load average |

## 6. Key Lessons Learned

Through this practical exercise, I learned that Linux provides built-in terminal commands that allow users and administrators to retrieve important information about a computer.

I also learned that:

1. Every Linux command has a specific purpose.
2. The terminal provides direct access to system information.
3. User accounts determine access privileges.
4. Linux directory paths are important for filesystem navigation.
5. Operating system and kernel versions are relevant to vulnerability research.
6. System architecture determines software compatibility.
7. Uptime and load averages provide useful information about system operation.

## 7. Practical Cybersecurity Applications

The commands practised in this exercise are useful during:

- Initial Linux system reconnaissance.
- Security auditing.
- System administration.
- Vulnerability assessment.
- Troubleshooting.
- Incident response.
- Software and security-tool compatibility checks.

These commands provide basic system information that can support more advanced security investigations.

## 8. Conclusion

This exercise introduced essential Linux system identification commands using Kali Linux.

The practical session established a foundation for understanding the Linux environment before proceeding to filesystem navigation, file management, permissions, users and groups, and package management.

Linux command-line proficiency is an important foundation for my continued development in cybersecurity, ethical hacking and penetration testing.

## 9. Evidence and Screenshots

Screenshots showing the execution and output of the seven commands are stored in the `screenshots/` directory of this module.

**Note:** Actual command outputs should be documented accurately. Example outputs in this report are illustrative and should not be presented as personally observed results unless they match the terminal output.

## 10. References

- [Kali Linux Official Documentation](https://www.kali.org/docs/)
- [Linux man-pages Project](https://www.kernel.org/doc/man-pages/)
- [GNU Coreutils Documentation](https://www.gnu.org/software/coreutils/manual/)
- [Linux Kernel Documentation](https://docs.kernel.org/)
