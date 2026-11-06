# IT Support Operations & Ticket Lifecycle Lab (Spiceworks Cloud)

## Project Overview
This project simulates real-world IT Support Desk operations within a sandboxed enterprise corporate environment (**CyberCorp**). By configuring a cloud-hosted ITSM platform, this lab demonstrates foundational help desk skills: ticket triage, incident categorization, user communication, and operational documentation. 

The tickets are based on the environments I built in my other labs: Active Directory, VLAN segmentation, and Group Policy.

## Core Configurations
-**Service Desk Setup:** Set up ticket categories for Identity & Access Management (AD/Azure), Network & Connectivity, Endpoint Hardening (GPO), and Hardware & Provisioning, and assigned a priority to each ticket.
Multi-User Simulation: Simulated tickets from different users across departments using Spiceworks’ #created by tag.
Documentation: Wrote an internal note on each ticket recording the cause, troubleshooting steps, and resolution.

## Documented Support Scenarios

### Scenario 1: Identity & Access Management (AD) Escalation (Ticket #3)
- **The Issue:** A Tier 1 administrator account was blocked when attempting to log into a high-security Tier 0 Domain Controller terminal.
- **The Resolution:** Verified the system event logs inside the **`CyberCorp.local`** domain. Confirmed the block was expected behavior under the tiered admin account structure from my Active Directory lab, which keeps Tier 1 (server) admin accounts separate from Tier 0 (domain) systems to limit how far a compromised account can reach. Documented the approved way to manage the domain controller remotely using Remote Server Administration Tools (RSAT).

### Scenario 2: Network & Subnet Connectivity Boundary (Ticket #4)
- **The Issue:** An HR end-user reported being unable to connect or print to an asset physically located inside the Finance department office network.
- **The Resolution:** Traced the connection timeout to the VLAN separation between departments. Confirmed network traffic isolation across distinct department subnets (HR: VLAN 10, Finance: VLAN 20) configured on a Cisco Catalyst 2960 switch to limit broadcast domains.

### Scenario 3: Endpoint Security & Malware Mitigation Block (Ticket #5)
- **The Issue:** An executive assistant reported a system-level policy block when attempting to launch a vendor billing script attachment (`Invoice_Archive.vbs`) received via email.
- **The Resolution:** Identified the attachment as a high-risk security threat. Documented that the execution loop was successfully caught and dropped by our active Group Policy baseline restricting Windows Script Host (`wscript.exe`) endpoints to block email-borne ransomware.

### Scenario 4: New-Hire Onboarding Request (Ticket #6)
- **The Issue:** HR requested immediate account provisioning and security group mapping for incoming enterprise user profiles ahead of orientation.
- **The Resolution:** Executed my custom modular PowerShell directory script to parse the HR roster data. The script programmatically cleared stale profiles, established the correct tiered Organizational Unit (OU) schema containers, generated secure randomized baseline credentials, and provisioned user access states directly into the **`CyberCorp.local`** directory without manual GUI configuration drift.

---

### Screenshot 1: Internal Note Security Audit Trail
<img width="1160" height="679" alt="Spiceworks Internal Ticket Audit Note" src="https://github.com/user-attachments/assets/9580277e-cb35-41c2-94bc-3a25b47094b2" />

### Screenshot 2: Closed Ticket Queue Dashboard View
<img width="1470" height="772" alt="Screenshot 2026-11-06 at 1 21 48 AM" src="https://github.com/user-attachments/assets/4eb3b2e1-2acf-4ee2-a4f6-142c0c8803d0" />



---

## Technical Skills Applied
- IT Service Management (ITSM) / ITIL Framework Alignment
- Ticket Lifecycle Triage & Prioritization Matrices
- Technical Help Desk Documentation (Internal Notes)
- Multi-User Escalation Workflows
