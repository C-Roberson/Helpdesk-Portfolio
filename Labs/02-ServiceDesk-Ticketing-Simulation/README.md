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

### Ticket #101: Account Lockout & Password Reset
* **User Issue:** User locked out of network domain after multiple failed login attempts.
* **Severity Level:** Low (Single user impact)
* **Category:** Identity & Access Management / Active Directory
* **Resolution Workflow:**
  1. Verified user identity following standard security verification protocols.
  2. Unlocked user account and forced password reset in administrative console.
  3. Advised user on updating stored credentials on mobile devices to prevent automated re-lockouts.
* **Customer Communication (Closure Note):**
  > "Hello [User], your account has been unlocked and a temporary password has been issued. Please log in using the temporary credentials and set a new password. If you experience further issues, reply directly to this ticket."

### Ticket #102: Remote Access / VPN Connection Failure
* **User Issue:** Remote worker unable to establish VPN tunnel to corporate network
* **Severity Level:** Medium (User unable to perform core duties remotely)
* **Category:** Network & Connectivity / VPN
* **Resolution Workflow:**
  1. Verified user's local internet connection was active.
  2. Inspected VPN client logs; identified stale authentication tokens and misconfigured gateway address.
  3. Guided user through clearing client cache and re-entering the primary VPN gateway server address.
* **Customer Communication (Closure Note):**
  > "Hi [User], we have updated your VPN configuration settings. Your connection has been verified and restored. Please let us know if you encounter any further connectivity drops."

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

