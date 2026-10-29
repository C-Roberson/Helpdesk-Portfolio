# Active Directory Enterprise Domain Deployment & Automation

## Project Overview & Objective
Designed and implemented an isolated enterprise domain environment (`home.lab`) using Oracle VM VirtualBox. The primary objective was to build a foundational identity management infrastructure, structure enterprise resources into logical Organizational Units (OUs) using PowerShell automation, and successfully integrate a client workstation to simulate real-world IT administration workflows.

---

## Tech Stack & Tools
* **Hypervisor:** Oracle VM VirtualBox (NAT Network with Promiscuous Mode enabled)
* **Operating Systems:** Windows Server 2022 Datacenter (Server Core), Windows 11 Pro for Workstation
* **Directory Services:** Active Directory Domain Services (AD DS), DNS, DHCP
* **Automation & Management:** PowerShell

---

## Troubleshooting Log
| **Symptom/Issue** | **Root Cause** | **Resolution** |
| :--- | :--- | :--- |
| Client workstation failed initial domain join with "The network path was not found." | The client virtual machine NIC was attached to a Bridged Adapter instead of the isolated NAT Network. | Switched the adapter settings back to the correct NAT Network, verified DNS connectivity using nslookup home.lab, and retried the domain join successfully. |
| PowerShell doesn't recognize `New-GPLink`, `New-GPO`, or `Get-GPO` commands on `DC01` | Windows Server Core is missing Group Policy PowerShell module | Install Remote Server Administration Tools (RSAT) feature for Group Policy on `DC01` via PowerShell then restart server. |
| Security banner GPO failed to apply to client workstation `FN-WS01` | The workstation was still in the default `Computers` container instead of newly created `Workstations` OU. | Moved client machine object to target OU via PowerShell. Verified the GPO registry key exists in AD. Returned to `FN-WS01`, ran `gpupdate /force`, then restarted machine and confirmed Security banner pops up as intended. |

---

## Phase 2: Group Policy Object (GPO) Deployment
To enforce baseline security, compliance, and custom user configurations across the environment, the following GPOs were deployed via PowerShell and linked to specific Organizational Units (OUs):

| GPO Name | Target OU | Enforcement Type | Description & Purpose |
| :--- | :--- | :--- | :--- |
| **`Workstation-Security-Banner`** | Workstations | Compliance | Displays a legal compliance warning notice prior to user login to satisfy organizational security requirements. |
| **`Workstation-Screensaver-Lock`** | Workstations | Endpoint Security | Enforces a 15 minute inactivity timeout with automatic screen locking to prevent physical unauthorized access to unattended endpoints. |
| **`Security-Block-USB`** | Finance | Data Protection | Prevents data exfiltration risks by restricting read and write access to unauthorized USB mass storage devices. |
| **`Security-Account-Lockout-Policy`** | Domain Wide | Brute-Force Mitigation | Automatically locks user account after 5 failed authentication attempts for 30 minutes to defend against credential-stuffing and brute-force attacks. |
| **`Security-Advanced-Audit-Policy`** | Domain Wide | Security Monitoring & SIEM Readiness | Enforces comprehensive auditing for logon/logoff event, privilege use, and account modifications to support security operations and event log forwarding. |
| **`Security-Restrict-Scripts`** | Workstations | Threat Mitigation | Hardens endpoints against malware execution by disabling Windows Script Host and restricting unauthorized script execution. |

---

## Environment Topology & Architecture

### 1. Network Topology (Virtual Infrastructure Layer)
* **Virtual Network:** NAT Network (`10.0.2.0/24`)
* **DC01 (Domain Controller):** Windows Server 2022 Core | Static IP: `10.0.2.10` | Preferred DNS: `127.0.0.1`
* **FIN-WS01 (Client Workstation):** Windows 11 Pro for Workstation | IP: `10.0.2.50` | Preferred DNS: `10.0.2.10`

```text
[ Router / Internet Gateway ]
             │
   [ VirtualBox Host ]
             │
   [ VirtualBox NAT Network ] (10.0.2.0/24 - Promiscuous Mode Enabled)
             │
             ├──► [ DC01 ]      (Windows Server 2022 Core | IP: 10.0.2.10 | DNS: 127.0.0.1)
             │                  └── Roles: Active Directory Domain Controller (home.lab) / DNS
             │
             └──► [ FIN-WS01 ]  (Windows 11 Pro for Workstation | IP: 10.0.2.50 | Preferred DNS: 10.0.2.10)
                                └── Role: Domain-Joined Client Workstation
```
---

## Logical Directory Structure (OU Hierarchy)
* Structured enterprise user and computer objects via PowerShell to prepare for future Group Policy (GPO) targeting:
```text
home.lab (Domain Root)
├── Finance (Departmental user accounts)
├── Marketing (Departmental user accounts)
├── HR (Human Resources user accounts)
├── IT (System administration and support staff)
├── Workstations (Domain-joined computer objects)
└── ServiceAccounts (Automated scripts and service accounts)
```
---

> **License**
>* This repository is open-source and available under the MIT License

---
