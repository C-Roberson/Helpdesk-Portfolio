# Standard Operating Procedure: New Hire Account Provisioning

* **Document ID:** SOP-IT-01
* **Applies To:** Tier 1 & Tier 2 Support Techs
* **Security Standard:** ISO 27001 Access Control Policy
* **Last Revised:** October 2026

---

## 1. Objective & Scope
Onboarding a new employee is more than just setting up an email address—it's about making sure they have secure, immediate access to the exact tools they need on day one without creating security blind spots. This guide covers our exact workflow for building user accounts, assigning base security groups, and syncing cloud licenses across Active Directory and Microsoft Entra ID.

---

## 2. Tools & Prerequisites
Before you start, make sure you have access to the following:
* The incoming HR onboarding ticket in Jira (must include written manager approval)
* Remote Server Administration Tools (RSAT) or direct access to Domain Controller `DC01`.
* The [Microsoft Entra ID Admin Center](https://entra.microsoft.com).
* PowerShell 5.1+ (for running our automated provisioning script).

---

## 3. Step-by-Step Provisioning Workflow

### Step 1: Verify the Paperwork First
Don't create any accounts until HR has officially signed off. 
1. Open up the Jira onboarding ticket. Double-check that the employee’s legal name, start date, department, and direct manager are clearly listed.
2. Verify that manager sign-off is attached. If anything is missing, bounce the ticket back to HR before proceeding.

### Step 2: Build the AD Object & Organizational Unit
We provision user objects directly in Active Directory. You can use our standard PowerShell script (`New-ADUser-Creation.ps1`) to handle this quickly, or do it manually via AD Administrative Center:
1. Navigate to the correct departmental OU: `Corp.local/Departments/[Department Name]/Users`
2. Set up the user using our naming convention: `firstname.lastname@company.com`.
3. Assign a secure temporary password and check the box forcing them to **change their password at first logon**.

*Quick PowerShell snippet for creating the account:*
```powershell
$SecurePassword = ConvertTo-SecureString "TempP@ssw0rd2026!" -AsPlainText -Force
New-ADUser -Name "Sarah Jenkins" `
           -GivenName "Sarah" `
           -Surname "Jenkins" `
           -SamAccountName "sjenkins" `
           -UserPrincipalName "sjenkins@lab.local" `
           -Path "OU=Finance,DC=lab,DC=local" `
           -AccountPassword $SecurePassword `
           -Enabled $true
```

### Step 3: Assign Baseline Group Memberships
Every employee needs baseline access before layering on department-specific tools. Head into the user properties and drop them into:
* `Domain Users` (Automatic baseline)
* `All-Company-Staff` (Distribution list)
* `Dept-[Name]-Read` (File Share Permissions)
**Security Warning:** Never drop a new hire into `Domain Admins` or local administrator groups unless there is an approved executive exception ticket on file.

### Step 4: Cloud Sync & License Assignment (Entra ID)
​Once Active Directory is updated, make sure the cloud tenant catches up:
1. If Azure AD Connect is lagging, force a manual delta sync from your server terminal:
`Start-ADSyncSyncCycle -PolicyType Delta`
2. Log into the Entra ID Portal, find the user, and assign their baseline Microsoft 365 license *(typically M365 Business Premium)*.
3. Push out standard SaaS apps (Slack, Jira, Zoom) via group-based licensing rules so they're waiting in their inbox.

### Step 5: Handoff & Ticket Closure
1. **Never** send plaintext temporary passwords through standard email or Slack. Use our secure password manager vault link instead.
2. Send the secure credentials directly to the hiring manager (not the employee directly, for security handoff protocol).
3. Update the Jira ticket to Resolved, drop in their assigned corporate email address, and tag it with `#Onboarding #Provisioned`

---
