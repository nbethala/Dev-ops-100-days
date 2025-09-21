# 🧑‍💻 Temporary User Creation on App Server 3

## Task Overview
Create a user named `ammar` on **App Server 3** in the **Stratos Datacenter** with the following specifications:

- Username: `ammar` (must be lowercase)
- Expiry Date: `2024-04-15`
- Ensure a home directory is created

## Steps Performed

1. **Accessed the Jump Server**:
   ```bash
   ssh jump_host

2. **Connected to App Server 3:**
    ```bash
    ssh appserver3

3. **Created the user with expiry and home directory:**
   ```bash
   sudo useradd -e 2024-04-15 -m ammar
   sudo passwd ammar

4. **Verified account expiration:**
    ```bash
   sudo chage -l ammar

 
