# Helpdesk-Portfolio
# Celeste Roberson | Help Desk Technician

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Profile-blue?style=flat&logo=linkedin)](https://linkedin.com/in/celesteroberson)
[![Email](https://img.shields.io/badge/Email-Contact_Me-red?style=flat&logo=gmail)](mailto:CQJ.Roberson@gmail.com)
[![Portfolio Site](https://img.shields.io/badge/GitHub_Pages-Live_Site-green?style=flat&logo=github)](https://github.com/C-Roberson/Helpdesk-Portfolio)

---

## 👩🏽‍💻 About Me
Help Desk Technician with 3+ years of experience in high-volume intake, transaction logging, and tier 1 customer support. Focused on systematic troubleshooting, continuous learning, and providing empathetic end-user support.

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
* **CompTIA A+** | CompTIA | *(In Progress)*

---

## 📂 Project Index

| Category | Project Title | Key Tools Used | Description |
| :--- | :--- | :--- | :--- |
| **Lab** | [01 - Display Hardware Diagnostics](./Labs/01-Display-Hardware-Diagnostics) | Windows Diagnostics, Display Drivers | Systematic troubleshooting and resolution of laptop panel issues. |
| **Lab** | [02 - ServiceDesk Ticketing Simulation](./Labs/02-ServiceDesk-Ticketing-Simulation) | ServiceDesk-Simulator.com | Ticket triage, severity categorization, user communication, and SLA management. |
| **Lab** | [03 - Active Directory Setup](./Labs/03-Active-Directory-Setup) | Oracle VirtualBox, Windows Server 2022, Windows 10/11, DNS | Deployed an isolated enterprise domain, provisioned OUs, and joined a client workstation completely through PowerShell automation. |
| **Documentation** | [MFA Enrollment Guide](./Knowledge-Base/MFA-Enrollment-Guide.md) | Markdown, ServiceNow, Microsoft 365 & Microsoft Authenticator | **End-User Communication:** Technical writing, user empathy, and ability to draft step-by-step self-service guides. |
| **Documentation** | [New Hire Account Provisioning SOP](./SOPs/New-Hire-Account-Provisioning-SOP.md) | Markdown, ServiceNow, Diagnostics & Command-Line Utilities | **Process Discipline:** Familiarity with administrative workflows, compliance frameworks, and secure identity management. |

---

## 🧪 Home Lab Architecture

```text
[ Router / Internet Gateway ]
             │
   ┌─────────┴─────────┐
   │  VirtualBox Host  │
   └─────────┬─────────┘
             |
   [ VirtualBox NAT Network ] (198.162.10.0/24 - Promiscuous mode enabled)
             |
             ├─► [ DC01 ]     (Windows Server 2022 Core | IP: 192.168.10.10 | Preferred DNS: 127.0.0.1)
             |                └── Roles: Active Directory Domain Controller (home.lab) / DNS / DHCP
             └─► [ FN-WS01 ]  (Windows 10/11 Pro | IP: 192.168.10.50 | Preferred DNS: 192.168.10.10)
                              └── Roles: Domain-Joined Client Workstation

