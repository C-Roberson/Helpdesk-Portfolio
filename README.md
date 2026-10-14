# Helpdesk-Portfolio
# Celeste Roberson | Technical Support Specialist

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-blue?style=flat&logo=linkedin)](https://linkedin.com/in/your-profile)
[![Email](https://img.shields.io/badge/Email-Contact_Me-red?style=flat&logo=gmail)](mailto:CQJ.Roberson@gmail.com)
[![Portfolio Site](https://img.shields.io/badge/GitHub_Pages-Live_Site-green?style=flat&logo=github)](https://C-Roberson.github.io/helpdesk-portfolio)

---

## 👩🏽‍💻 About Me
Technical Support Specialist with 3+ years of experience in high-volume intake, transaction logging, and tier 1 customer support. Focused on systematic troubleshooting, continuous learning, and providing empathetic end-user support.

---

## 🛠️ Technical Skills

* **Systems & Administration:** Active Directory, User Provisioning, Windows 10/11, macOS, Linux, System Administration and Security
* **Service Desk Operations:** Ticketing and Queue Operations, Triage and Escalation, System Documentation, Case Management
* **Networking & Hardware:** TCP/IP, DNS, DHCP, VPNs, Hardware Diagnostics & Maintenance, Peripheral Setup, System Diagnostics
* **Scripting & Command Line:** PowerShell, Windows CMD, Bash
* **Technical Support:** Tier 1 Customer Support, Troubleshooting, User Intake, Incident De-escalation, Technical Communication

---

## 📜 Certifications
* **Google IT Support Professional Certificate** | Coursera | *Sept 2026*
* **CompTIA A+** | CompTIA *(In Progress)*

---

## 📂 Project Index

| Category | Project Title | Key Tools Used | Description |
| :--- | :--- | :--- | :--- |
| **Lab** | [01 - Display Hardware Diagnostics](./Labs/01-Display-Hardware-Diagnostics) | Windows Diagnostics, Display Drivers | Systematic troubleshooting and resolution of laptop panel issues. |
| **Lab** | [02 - ServiceDesk Ticketing Simulation](./Labs/02-ServiceDesk-Ticketing-Simulation) | (ServiceDesk-Simulation.com) | Ticket triage, severity categorization, user communication, and SLA management. |
| **Documentation** | [MFA Setup Guide](./Knowledge-Base/MFA-Enrollment-Guide.md) | Technical Writing, Security | End-user self-service guide for enrolling in Multi-Factor Authentication. |
| **Automation** | [New AD User Script](./Scripts/New-ADUser-Creation.ps1) | PowerShell, Active Directory | Script automating bulk user provisioning and organizational unit assignment. |

---

## 🧪 Home Lab Architecture

```text
[ Router / Internet Gateway ]
             │
   ┌─────────┴─────────┐
   │ VirtualBox Host   │
   └─────────┬─────────┘
             ├─► [ Windows Server 2022 ] (Domain Controller / Active Directory / DNS / DHCP)
             └─► [ Windows 11 Client ]   (Domain-Joined / Test Workstation)

