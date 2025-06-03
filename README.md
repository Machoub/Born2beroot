# 🛡️ Born2beroot – 42 Project

---

## 📌 Project Description

**Born2beroot** is an introductory system administration project at **École 42**.  
The goal is to install and configure a secure virtual machine from scratch using **Debian** or **Rocky Linux**, without any GUI, and to implement strict system hardening best practices.

By completing this project, students explore the world of virtualization, partitioning (including LVM and encrypted disks), user and permission management, firewall configuration, SSH, password policies, and Bash scripting.

---

## 📅 Status

- **Finished**: December 21, 2023  
- **Grade**: 125%

---

## 🖥️ Requirements

- Virtualization platform: **Oracle VirtualBox 6.1**
- OS: **Debian 11.2.0**
- At least 20GB of free disk space
- No GUI installed (X.org and equivalents are strictly forbidden)

---

## 🔧 What Was Implemented

### 🔐 Security Configuration

- SSH on **port 4242**, root login disabled
- Strong password policy (10+ chars, expiration, complexity, no reuse)
- Custom sudo configuration:
  - Max 3 attempts
  - Custom error message
  - Command input/output logging to `/var/log/sudo/`
  - TTY required
  - Secure PATH enforced

### 🧱 System Setup

- Partitioning with encrypted **LVM**
- Separate logical volumes for `/`, `/home`, `/var`, `/tmp`, `/boot`
- Use of `AppArmor` (Debian) or `SELinux` (Rocky)
- Custom hostname: `machouba42`
- UFW configured with only **port 4242** open

### 👤 User Management

- `machouba` user in `sudo` and `user42` groups
- Password policies enforced via `pam_pwquality`
- Sudo rights limited and logged

### 📊 Monitoring Script

Custom `monitoring.sh` script that:
- Displays system info via `wall` every 10 minutes
- Includes architecture, CPU, memory/disk usage, last boot, LVM status, TCP connections, active users, IP/MAC address, and sudo command count
- Scheduled with `cron`
- No errors allowed during execution

---

## 🏅 Bonus Features

- ✅ SSH authentication via key pair
- ✅ Advanced partition scheme
- ✅ Custom system logging and alerts
- ✅ Clean cronjob automation
- ✅ Password complexity + expiration policies fully applied
- ✅ Monitoring script meeting all subject requirements

---

## 📦 Deliverables

- ✅ `signature.txt` file with correct SHA1 hash of the VM disk
- ✅ GitHub repository with clean README and no VM files included
- ✅ Fully functional VM matching all evaluation constraints

---

## 🧠 Lessons Learned

- System installation and secure configuration from scratch
- Linux security best practices (sudo, PAM, firewalls, SSH hardening)
- Bash scripting with real use cases
- LVM, partitions and disk management
- Cron automation and process scheduling
- OS-level monitoring and logging

---

## 📚 Guides & References

- [Debian Installation Manual](https://www.debian.org/releases/)
- [Linux PAM Documentation](https://linux.die.net/man/8/pam_pwquality)
- [UFW Documentation](https://help.ubuntu.com/community/UFW)

---

## 👨‍💻 Author

**Mehdi Adel Achouba**
42 Paris – Login: machouba
