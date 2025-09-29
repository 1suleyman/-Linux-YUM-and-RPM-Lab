# 🐧 Linux YUM and RPM Lab

In this lab, I worked on **CentOS 9** to understand package management with **RPM** and **YUM**. I learned how to query packages, install software, and inspect configured repositories on a Linux system.

---

## 📋 Lab Overview

**Goal:**

* Learn how to manage packages using RPM and YUM
* Install third-party applications like Firefox
* Query package names, versions, and dependencies
* Inspect configured software repositories

**Learning Outcomes:**

* Identify package manager commands for RPM and YUM
* Install and verify software packages
* Handle permissions issues using `sudo`
* List repositories and determine which packages provide specific commands

---

## 🛠 Step-by-Step Journey

### Step 1: Access the CentOS Lab Server

**Task:** SSH into the CentOS server.

**Command:**

```bash
ssh username@server_ip
```

* Enter password when prompted
* Confirm successful login

💡 **Tip:** Username/IP can vary; always refer to provided infrastructure details.

---

### Step 2: Identify the Package Manager

**Observation:**

* CentOS uses **YUM** and **RPM** as package managers.
* Commands like `yum install <package>` and `rpm -q <package>` are standard.

---

### Step 3: Query Installed Packages with RPM

**Task:** Find exact package names.

**Command:**

```bash
rpm -q wget
```

* Output example: `wget-1.21.2-1.el9.x86_64`
* Useful to verify installed versions and exact package names.

---

### Step 4: Install Software with RPM and YUM

**Attempt 1:** RPM Installation

```bash
sudo rpm -ivh /home/username/Firefox-xx.rpm
```

* May fail due to missing dependencies or permissions
* Error messages: "Dependencies not met" or "File corrupted"

**Attempt 2:** YUM Installation (preferred)

```bash
sudo yum install firefox
```

* Handles dependencies automatically
* Prompts for confirmation → type `y` to continue
* Installation completes successfully

💡 **Tip:** YUM simplifies package installation by resolving dependencies, whereas RPM is low-level and requires manual handling.

---

### Step 5: List Configured Repositories

**Task:** Determine the number of software repositories configured.

**Command:**

```bash
yum repolist
```

* Example output: 6 repositories available
* Allows understanding of where packages are pulled from

---

### Step 6: Identify Package Providing a Command

**Task:** Find which package provides a given command (e.g., `tcpdump`).

**Command:**

```bash
yum provides tcpdump
```

* Output shows package name and version, e.g., `tcpdump-4.9.0-9.el9.x86_64`
* Helpful for troubleshooting missing commands

💡 **Tip:** Use `yum provides` or `rpm -qf <file>` to locate packages that contain specific commands or files.

---

## ✅ Key Commands Summary

| Task                               | Command                              |
| ---------------------------------- | ------------------------------------ |
| SSH into server                    | `ssh username@server_ip`             |
| Query installed package            | `rpm -q <package>`                   |
| Install RPM package                | `sudo rpm -ivh /path/to/package.rpm` |
| Install with dependency resolution | `sudo yum install <package>`         |
| List configured repositories       | `yum repolist`                       |
| Find package providing a command   | `yum provides <command>`             |

---

## 💡 Notes / Tips

* Always use `sudo` for system-level installations.
* RPM can install packages manually but may fail if dependencies are missing.
* YUM handles dependencies automatically and is the preferred method on CentOS/RHEL.
* The lab highlights how to query, install, and troubleshoot packages in a Linux environment.

---

## ✅ References

* [RPM Documentation](https://rpm.org/documentation.html)
* [YUM Documentation](https://linux.die.net/man/8/yum)
* [Installing Packages with YUM](https://www.centos.org/docs/)

