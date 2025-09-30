
# Password-less SSH Access Setup

This project configures password-less SSH authentication from the `thor` user on a **jump host** to multiple **app servers** through their respective **sudo users**. It enables secure, automated access for remote administration and deployment.

## 🔐 Objective

Allow `thor@jump-host` to SSH into each app server as its sudo user (e.g., `appadmin@app1`) without entering a password, and execute `sudo` commands without password prompts.

## 🛠️ Setup Steps

### 1. Generate SSH Key on Jump Host

```bash
ssh-keygen -t rsa -b 4096 -C "thor@jump-host"
Save to default location (~/.ssh/id_rsa)

Leave passphrase empty for password-less access

2. Copy Public Key to App Servers
bash
ssh-copy-id appadmin@app1
ssh-copy-id appadmin@app2
Repeat for each app server.

3. Configure SSH ProxyJump (Optional)
Edit ~/.ssh/config on the jump host:

bash
Host app1
    HostName app1.internal
    User appadmin
    ProxyJump thor@jump-host

Host app2
    HostName app2.internal
    User appadmin
    ProxyJump thor@jump-host
4. Enable Password-less Sudo on App Servers
Edit sudoers file:

bash
sudo visudo
Add:

bash
appadmin ALL=(ALL) NOPASSWD:ALL
5. Test Access
From the jump host:

bash
ssh appadmin@app1
sudo whoami
Expected output:

Code
root
✅ Result
thor can SSH into app servers via sudo users without password

sudo commands execute without password prompts

Secure and efficient access for automation and remote management

📁 Files
~/.ssh/id_rsa — Private key

~/.ssh/id_rsa.pub — Public key

~/.ssh/config — SSH configuration

/home/appadmin/.ssh/authorized_keys — Remote key store

🔒 Security Notes
Ensure private key (id_rsa) is protected: chmod 600 ~/.ssh/id_rsa

Restrict sudo access to trusted users only

Consider using firewall rules or SSH hardening for added security
