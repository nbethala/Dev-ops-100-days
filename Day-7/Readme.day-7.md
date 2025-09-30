
# Ansible 4.9.0 Setup on Jump Host

This guide documents the installation of **Ansible version 4.9.0** on a Jump host using `pip3`, ensuring the binary is globally accessible to all users.

---

## 📦 Installation Steps

1. **Update System & Install pip3**
   ```bash
   sudo apt update
   sudo apt install python3-pip -y
   
2. **Install Ansible 4.9.0 Globally**

sudo pip3 install ansible==4.9.0

3.**Verify Installation**

ansible --version
Expected output:

Code
ansible [core 2.11.x]
  config file = /etc/ansible/ansible.cfg
  
4. **Ensure Global Access (if needed) If ansible is not globally available: **

sudo ln -s /usr/local/bin/ansible /usr/bin/ansible

🧪 Test Ansible
Run a simple ping test:

```bash
ansible localhost -m ping
📁 Notes
This setup uses pip3 for flexibility and version control.

All users on the system can run Ansible commands.

For privilege escalation in playbooks, users must have appropriate sudo rights.
