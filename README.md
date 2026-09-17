# Helpdesk-Portfolio
# Celeste Roberson | Help Desk Technician

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-blue?style=flat&logo=linkedin)](https://linkedin.com/in/your-profile)
[![Email](https://img.shields.io/badge/Email-Contact_Me-red?style=flat&logo=gmail)](mailto:CQJ.Roberson@gmail.com)
[![Portfolio Site](https://img.shields.io/badge/GitHub_Pages-Live_Site-green?style=flat&logo=github)](https://C-Roberson.github.io/helpdesk-portfolio)

---

## 👩🏽‍💻 About Me
Detail-oriented **Help Desk Technician** with a strong foundation in hardware/software troubleshooting, user administration, and ticketing workflows. Experienced in delivering clear customer support, resolving technical incidents, and maintaining comprehensive technical documentation.

---

## 🛠️ Technical Skills

* **Systems & Administration:** Active Directory, User Provisioning, Windows 10/11, macOS, Linux, System Administration and Security
* **Service Desk Operations:** Ticketing and Queue Operations, Triage and Escalation, System Documentation, Case Management
* **Networking & Hardware:** TCP/IP, DNS, DHCP, VPNs, Hardware Diagnostics & Maintenance, Peripheral Setup, System Diagnostics
* **Scripting & Command Line:** PowerShell, Windows CMD, Bash
* **Technical Support:** Tier 1 Customer Support, Troubleshooting, User Intake, Incident De-escalation, Technical Communication

---

## 📜 Certifications
* **Google IT Support Professional Certificate** | Google *(In Progress)*
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

