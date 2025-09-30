# Nautilus Cron Job Deployment Test

This project is a preliminary test for deploying automated scripts via cron jobs across all application servers in the Stratos DC. The goal is to validate scheduled task execution before rolling out full automation.

## 📋 Objectives

- Install and configure `cronie` on all app servers
- Enable and start the `crond` service
- Add a sample cron job for the root user to verify functionality

## 🛠️ Setup Instructions

### 1. Install `cronie` Package

Run the following on each app server:

```bash
sudo yum install -y cronie

2. Start and Enable crond Service
bash
sudo systemctl enable crond
sudo systemctl start crond
3. Add Sample Cron Job
Switch to the root user and add the following cron job:

bash
crontab -e
Add this line:

Code
*/5 * * * * echo hello > /tmp/cron_text
This job writes "hello" to /tmp/cron_text every 5 minutes.

🔍 Verification
To confirm the cron job is working:

bash
cat /tmp/cron_text
Check timestamps or content updates every 5 minutes.

👥 Server Access
Use the following credentials from the jump host:

ssh tony@stapp01

ssh steve@stapp02

ssh banner@stapp03

Use sudo for administrative tasks.

📌 Notes
Ensure time synchronization across servers for consistent cron execution.

Logs can be checked via /var/log/cron for troubleshooting.
