# 🔒 SSH Root Login Hardening - Stratos Datacenter

## 📋 Task Overview

The objective was to enhance security by **disabling direct SSH root login** on all application servers within the **Stratos Datacenter**.

## 🖥️ Target Servers

- `stapp01.stratos.xfusioncorp.com`
- `stapp02.stratos.xfusioncorp.com`
- `stapp03.stratos.xfusioncorp.com`

## 🛠️ Steps Performed

1. **Logged into each server** using a non-root user with sudo privileges.
2. **Edited the SSH configuration file**:
   ```bash
   sudo vi /etc/ssh/sshd_config
   
3. **Modified the following directive:**
   ```bash
   - PermitRootLogin yes
   + PermitRootLogin no

4. **Saved the file and restarted the SSH service:**
   ```bash
   sudo systemctl restart sshd

5. **Verified the change by attempting SSH login as root:**
   ```bash
   ssh root@<server>

✅ Outcome
Direct SSH root login is now disabled on all app servers, aligning with security best practices and compliance requirements.

