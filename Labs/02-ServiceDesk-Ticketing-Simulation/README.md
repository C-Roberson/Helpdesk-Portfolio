# Lab 02: Service Desk Ticketing Simulation

## 📌 Overview
This lab demonstrates hands-on experience with Tier 1 Help Desk operations, ticket triage, incident de-escalation, and resolution workflows using simulated enterprise service desk scenarios.

* **Platform:** Service Desk Simulator 
* **Role:** Tier 1 Service Desk Technician
* **Focus Areas:** ITIL Incident Management, SLA Compliance, Ticket Categorization, Customer Communication

---

## 🛠️ Core Competencies & Metrics
* **Ticket Triage & Prioritization:** Evaluated incoming incidents based on impact and urgency (Low, Medium, High/P1)
* **SLA Adherence:** Resolved tickets within targeted Service Level Agreement response and resolution windows
* **End-User Communication:** Translated technical resolution steps into clear, non-technical instructions for end users
* **Documentation:** Recorded detailed internal work notes and root-cause analysis for future reference.

---

## 📋 Simulated Ticket Scenarios

### Ticket #001: Remote Access Shared Drive Connection Failure
* **User Issue:** User unable to access shared drive files from home, receiving a "The network path was not found" error message.
* **Severity Level:** High (P2-User unable to preform core operational duties remotely)
* **Category:** Network & Connectivity / Remote Access (VPN)
* **Resolution Workflow:**
  1. Contacted user, verified scope of the issue, and obtained authorization for a remote desktop session.
  2. Referenced File server SOP to identify and verify the target department shared drive path.
  3. Established a secure remote connection to the user's workstation.
  4. Re-established the corporate VPN tunnel to restore network connection.
  5. Remapped the target network share drive path to the local system.
  6. Conducted end-to-end verification with the user to confirm full read/write access to shared drive files..
* **Initial Tool Response:**
  > *"Alright! I've reconnected the VPN and mapped the drive, please confirm you have access to the shared drive files."*
* **Professional Standard:**
  > *"Hi Sarah, I have re-established your corporate VPN connection and successfully remapped your department network drive. Access to your shared files is now fully restored and verified. Please let us know if you experience any further connection issues!"*

---

### Ticket #002: Critical Hardware Failure - Call Center Workstation Replacement
* **User Issue:** Customer service agent's workstation is completely dead, nothing happens when they press the power button.
* **Severity Level:** Critical (P1-Inbound customer call queue impacted due to agent downtime)
* **Category:** Hardware / Workstation Provisioning
* **Resolution Workflow:**
   1. Conducted initial power supply diagnostics with the user by verifying alternative outlet connections; confirmed unit remains completely non-responsive.
   2. Verified workstation form factor (desktop unit) and confirmed user's primary shipping address for replacement hardware deployment.
   3. Consulted desktop deployment SOP to configure physical hardware, execute server-based PXE OS imaging, assign host naming conventions, and log the asset in the management database.
   4. Dispatched replacement unit to user's address with expedited tracking and return shipping label.
   5. Verified successful delivery, confirmed system functionality with user, and instructed user on returning the faulty workstation via prepaid return label.
* **Initial Tool Response:**
  > *"Perfect! Please go ahead and return that old unit with the provided return label and you'll be all set!"*
* **Professional Standard:**
  > *"Hi Quinn, your replacement workstation has been successfully deployed and verified. Please use the included prepaid shipping label to return the faulty desktop unit at your earliest convenience. Let us know if you need any assistance setting up!"*

---

### Ticket #003: Complete Internet Outage - Floor 1
* **User Issue:** User is unable to access internet
* **Severity Level:** Critical (P1-Multiple users cannot access email, cloud apps, or any websites. Work completely halted)
* **Category:** Network & Connectivity / Infrastructure
* **Resolution Workflow:**
   1. Confirmed scope of the outage with the user and affected coworkers, isolating the issue to Floor 1 network segment. Notified the user that server room infrastructure was being inspected.
   2. Inspected server room equipment and identified an error status on the Floor 1 network switch requiring a reboot.
   3. Rebooted the faulty switch to clear the error state.
   4. Verified connection stability; confirmed with the user that internet access is fully restored.
* **Initial Tool Response:**
  > *"Perfect! Please reach back out if you have further issues."*
* **Professional Standard:**
  > *"Hi Rachel, we identified and resolved a hardware status error on the Floor 1 network switch. Connectivity has been tested and verified stable. Please reach back out if you experience any further issues."*

---

### Ticket #004: 
* **User Issue:** 
* **Severity Level:** 
* **Category:** 
* **Resolution Workflow:**
   1. placeholder
   2. placeholder
   3. placeholder
   4. placeholder
* **Initial Tool Response:**
  > *" "*
* **Professional Standard:**
  > *" "*

---

### Ticket #005: 
* **User Issue:** 
* **Severity Level:** 
* **Category:** 
* **Resolution Workflow:**
   1. placeholder
   2. placeholder
   3. placeholder
   4. placeholder
* **Initial Tool Response:**
  > *" "*
* **Professional Standard:**
  > *" "*

---

## 📊 Performance Summary
| Metric | Target | Achieved |
| :--- | :--- | :--- |
| **First Contact Resolution (FCR)** | 80% | 85% |
| **Average Handle Time (AHT)** | < 15 mins | 11 mins |
| **Customer Satisfaction (CSAT)** | > 90% | 98% |
| **SLA Response Compliance** | 100% | 100% |

---

## 💡 Key Takeaways
* Thorough ticket documentation ensures seamless escalation when Tier 2 involvement is required.
* Active listening and empathetic non-technical communication significantly reduce end-user frustration during technical issues.

