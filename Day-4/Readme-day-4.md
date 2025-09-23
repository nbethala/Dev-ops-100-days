
### 📝 Exercise: File Permissions in Linux

**Question:**  
Grant executable permissions to the `/tmp/xfusioncorp.sh` script on *App Server 2*.  
Ensure that **all users** have the capability to execute it.

**Initial State:**  
---------- 1 root root ...

Code

**Attempt:**  
```bash
chmod a+x /tmp/xfusioncorp.sh
Resulted in:

Code
---x--x--x
This allowed execute only, but scripts also require read permission so the interpreter (e.g. /bin/bash) can open the file.

Correct Answer:

bash
sudo chmod a+rx /tmp/xfusioncorp.sh
or equivalently:

bash
sudo chmod 555 /tmp/xfusioncorp.sh
Final Permissions:

Code
-r-xr-xr-x 1 root root ...
✅ Now all users can both read and execute the script, which satisfies the requirement.

Code

---
