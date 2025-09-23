# Project Task: Following a security audit, the xFusionCorp Industries security team has opted to enhance application and server security with SELinux. 
# To initiate testing, the following requirements have been established for App server 3 in the Stratos Datacenter:


# Install the required SELinux packages.

Permanently disable SELinux for the time being; it will be re-enabled after necessary configuration changes.

No need to reboot the server, as a scheduled maintenance reboot is already planned for tonight.

Disregard the current status of SELinux via the command line; the final status after the reboot should be disabled.

## Solution : 
# SELinux Setup and Configuration (CentOS Stream)

---

## 1. Check Operating System

To verify which Linux distribution is running:


cat /etc/os-release

```bash
NAME="CentOS Stream"
VERSION="9"
ID="centos"
```

## 2. Install SELinux Packages
```bash
sudo dnf install -y policycoreutils selinux-policy selinux-policy-targeted
```

## 3. Permanently Disable SELinux
```bash
sudo nano /etc/selinux/config

SELINUX=disabled
SELINUXTYPE=targeted



