# Active Directory Enterprise Domain Deployment & Automation

## 🎯 Project Overview & Objective
Designed and implemented an isolated enterprise domain environment (`home.lab`) using Oracle VM VirtualBox. The primary objective was to build a foundational identity management infrastructure, structure enterprise resources into logical Organizational Units (OUs) using PowerShell automation, and successfully integrate a client workstation to simulate real-world IT administration workflows.

---

## 🛠️ Tech Stack & Tools
* **Hypervisor:** Oracle VM VirtualBox (NAT Network with Promiscuous Mode enabled)
* **Operating Systems:** Windows Server 2022 Datacenter (Server Core), Windows 11 Pro for Workstation
* **Directory Services:** Active Directory Domain Services (AD DS), DNS, DHCP
* **Automation & Management:** PowerShell

---

## 🗺️ Environment Topology & Architecture

### 1. Network Topology (Virtual Infrastructure Layer)
* **Virtual Network:** NAT Network (`192.168.10.0/24`)
* **DC01 (Domain Controller):** Windows Server 2022 Core | Static IP: `192.168.10.10` | Preferred DNS: `127.0.0.1`
* **FIN-WS01 (Client Workstation):** Windows 11 Pro for Workstation | IP: `192.168.10.50` | Preferred DNS: '192.168.10.10'

```text
[ Router / Internet Gateway ]
             │
   [ VirtualBox Host ]
             │
   [ VirtualBox NAT Network ] (192.168.10.0/24 - Promiscuous Mode Enabled)
             │
             ├──► [ DC01 ]      (Windows Server 2022 Core | IP: 192.168.10.10)
             │                  └── Roles: Active Directory Domain Controller (home.lab) / DNS
             │
             └──► [ FIN-WS01 ]  (Windows 11 Pro for Workstation | IP: 192.168.10.50)
                                └── Role: Domain-Joined Client Workstation

```text
home.lab (Domain Root)
├── Finance (Departmental user accounts)
├── Marketing (Departmental user accounts)
├── HR (Human Resources user accounts)
├── IT (System administration and support staff)
├── Workstations (Domain-joined computer objects)
└── ServiceAccounts (Automated scripts and service accounts)

---

## 🔧 Troubleshooting Log
| **Symptom/Issue** | **Root Cause** | **Resolution** |
| Client workstation failed initial domain join with "The network path was not found." | The client virtual machine NIC was attached to a Bridged Adapter instead of the isolated NAT Network. | Switched the adapter settings back to the correct NAT Network, verified DNS connectivity using nslookup home.lab, and retried the domain join successfully. | 

---

```text
## 📃 License
This repository is open-source and available under the MIT License.
