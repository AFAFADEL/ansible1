# 🚀 Multi-Playbook Orchestration Lab

## 📌 Overview
This project demonstrates how to automate infrastructure tasks using **Ansible Playbooks**.  
It combines service configuration and monitoring deployment into a single automated workflow.

---

## 🧩 Project Structure


project/
│
├── services.yml # Web server setup (Nginx stop + Lighttpd install)
├── monitoring.yml # System monitoring dashboard deployment
├── main.yml # Master playbook (orchestration)
├── inventory.ini # Target hosts
├── metrics.sh # System metrics script
├── style.css # Dashboard styling
└── index.html # Dashboard template


---

## ⚙️ Phase 1: Services Configuration (`services.yml`)

This playbook performs the following tasks:

- Stops **Nginx** service to avoid port conflicts
- Installs **Lighttpd web server**
- Starts and enables Lighttpd on boot

### ▶️ Key Tasks:
```yaml
- Stop nginx service (if exists)
- Install lighttpd package
- Start and enable lighttpd
📊 Phase 2: Monitoring Setup (monitoring.yml)

This playbook is responsible for:

Copying system metrics script to remote servers
Executing the script to collect CPU, RAM, and Disk usage
Deploying a styled web dashboard
Personalizing the dashboard with student input
🔗 Phase 3: Master Playbook (main.yml)

The main playbook orchestrates the full workflow:

- import_playbook: services.yml
- import_playbook: monitoring.yml
🎯 Purpose:

Ensures tasks run in the correct sequence:

Configure web server
Deploy monitoring system
▶️ How to Run

Execute the full automation using:

ansible-playbook -i inventory.ini main.yml --ask-become-pass

You will be prompted to enter your name for dashboard branding.

🌐 Output

After successful execution:

Lighttpd web server is running
Monitoring dashboard is deployed
System metrics (CPU, RAM, Disk) are displayed in real time
Dashboard is accessible via browser:
http://<server-ip>
🛠️ Prerequisites

Ensure the following are installed:

Ansible
SSH access to target machines
Python on remote hosts
Required files:
metrics.sh
style.css
index.html
🎓 Learning Outcomes

By completing this lab, you will understand:

Ansible playbook modularization
Service management (systemd)
Package installation automation
File deployment using Ansible
Playbook orchestration using import_playbook
<img width="2556" height="1439" alt="ansible1" src="https://github.com/user-attachments/assets/c0436709-cef9-4c8b-9ace-309596764a2c" />
<img width="2543" height="1208" alt="ansible2" src="https://github.com/user-attachments/assets/7190f105-43cf-4ea2-a752-05f2e8a09ca4" />
