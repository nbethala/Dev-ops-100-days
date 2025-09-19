# 100 Days of DevOps – Day 1

## 🗓 Date
2025‑09‑19

## 📌 Task
**Create a user named `john` with a non‑interactive shell on App Server 1.**

## 🛠 Steps Taken
1. **Connected to App Server 1**  
   ```bash
   ssh tony@stapp01

2.**0Created the user with /sbin/nologin shell**
sudo useradd -s /sbin/nologin john

3.**Verified the user**
grep john /etc/passwd
john:x:1002:1002:Non-interactive service account:/home/john:/sbin/nologin



