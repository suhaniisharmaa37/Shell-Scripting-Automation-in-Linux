# 🛠️ System Maintenance Automation Script

### **File:** `system_maintenance_automation.sh`

---

## 📋 **Overview**
This Bash script automates the setup and maintenance of essential server components on a Linux system. It installs and configures services like **Apache**, **NGINX**, **MySQL**, **Bind9 DNS**, and **vsftpd FTP**, while also performing routine maintenance tasks such as system updates, disk checks, log cleanup, backups, and automated scheduling.

---

## 🚀 **Features**

- 🔧 Automated installation and configuration of:
  - Apache Web Server  
  - NGINX Web Server  
  - MySQL Database Server  
  - Bind9 DNS Server  
  - vsftpd FTP Server  

- 🧹 System maintenance tasks:
  - Package updates  
  - Disk space monitoring  
  - Log cleanup (older than 30 days)  
  - Backup of web files using `rsync`  
  - Restarting web services  

- 🕒 Automatic daily scheduling via **Crontab**

- 📜 Logging of all actions to:
  ```
  /var/log/system_maintenance_automation.log
  ```

- 📧 (Optional) Email reports can be sent automatically (requires mail utilities).

---

## ⚙️ **Requirements**

| Requirement | Description |
|--------------|-------------|
| OS | Ubuntu/Debian-based Linux |
| Privileges | Root or sudo access |
| Tools | `apt`, `rsync`, `cron`, `mailx` (optional) |

---

## 🧰 **Installation & Usage**

### 1️⃣ **Clone or Download the Script**
```bash
git clone https://github.com/<yourusername>/system-maintenance-automation.git
cd system-maintenance-automation
```

### 2️⃣ **Make Script Executable**
```bash
chmod +x system_maintenance_automation.sh
```

### 3️⃣ **Run the Script**
```bash
sudo ./system_maintenance_automation.sh
```

> The script will ask for confirmation before proceeding with installation and maintenance.

---

## 🗂️ **Log File**
All actions performed by the script are logged in:
```
/var/log/system_maintenance_automation.log
```

---

## 🕓 **Automated Scheduling**
After the first run, the script automatically adds a **daily cron job**:
```
0 0 * * * /bin/bash /path/to/system_maintenance_automation.sh
```
This ensures daily maintenance tasks are performed automatically at midnight.

---

## 📦 **Backup Details**
Backups are stored in:
```
/backup/apache_www_backup/
```
It contains a copy of all files from:
```
/var/www/html
```

---

## 📧 **Email Reporting (Optional)**
If `mailx` or `mailutils` is configured, uncomment the line at the end of the script to send maintenance reports:
```bash
mailx -a $LOG -s "Daily System Maintenance Report" sysadmin@example.com
```

---

## 🧾 **Example Output (Excerpt)**
```
----- System Maintenance Automation -----
Updating packages...
Installing Apache...
Installing NGINX...
Installing MySQL...
Running disk space check...
Cleaning old log files...
Restarting web services...
Backup completed.
Daily maintenance job scheduled in crontab.
----- Script Finished -----
```

---

## 🧑‍💻 **Author**
**Suhani Sharma**  
BCA, Semester 5 — Linux Administration Lab (23CAP-305)  
Instructor: **Mr. Rajat Kapoor**  

---

## 🌐 **References**
- [GitHub Repository](https://github.com/yourusername/system-maintenance-automation)  
- [LinkedIn Profile](https://www.linkedin.com/in/your-linkedin-id)

---

## ⚠️ **Disclaimer**
> Use this script at your own risk. Always review and modify configurations according to your system’s requirements before executing. Running this script on a production environment without testing may cause unintended changes.
