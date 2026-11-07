# IT Support Operations & Ticket Lifecycle Lab (Spiceworks Cloud)

## Project Overview
This project simulates real-world IT Support Desk operations within a sandboxed enterprise corporate environment (**CyberCorp**). By configuring a cloud-hosted ITSM platform, this lab demonstrates foundational help desk skills: ticket triage, incident categorization, user communication, and operational documentation. 

### Closed Ticket Queue
<img width="1463" height="803" alt="Screenshot 2026-11-06 at 7 21 30 PM" src="https://github.com/user-attachments/assets/fd10cbaa-7fb2-49be-86b1-d54e4004f103" />

The tickets are based on the environments I built in my other labs: Active Directory, VLAN segmentation, and Group Policy.

## Core Configurations
- **Service Desk Setup:** Set up ticket categories for Identity & Access Management (AD/Azure), Network & Connectivity, Endpoint Hardening (GPO), and Hardware & Provisioning, and assigned a priority to each ticket.
- **Multi-User Simulation:** Simulated tickets from different users across departments using Spiceworks’ #created by tag.
- **Documentation:** Wrote an internal note on each ticket recording the cause, troubleshooting steps, and resolution.

## Documented Support Scenarios

### Scenario 1: Identity & Access Management (AD) Escalation (Ticket #3)
- **The Issue:** A Tier 1 administrator account was blocked when attempting to log into a high-security Tier 0 Domain Controller terminal.
- **The Resolution:** Verified the system event logs. Confirmed the block was expected: accounts without the “Allow log on locally” right can’t sign in at a domain controller, and my tiered admin OU design keeps Tier 1 (server) admin accounts separate from Tier 0 (domain) systems. Documented the approved way to manage the domain controller remotely using Remote Server Administration Tools (RSAT).

### Scenario 2: Network & Subnet Connectivity Boundary (Ticket #4)
- **The Issue:** An HR end-user reported being unable to connect or print to an asset physically located inside the Finance department office network.
- **The Resolution:** Traced the connection timeout to the VLAN separation between departments (HR: VLAN 10, Finance: VLAN 20) configured on a Cisco Catalyst 2960 switch in my network lab, which keeps department traffic separate.

### Scenario 3: Endpoint Security & Malware Mitigation Block (Ticket #5)
- **The Issue:** An executive assistant reported a system-level policy block when attempting to launch a vendor billing script attachment (`Invoice_Archive.vbs`) received via email.
- **The Resolution:** Identified the attachment as a risky file type. Confirmed the block was expected: my Group Policy baseline disables Windows Script Host, which stops email-borne script attachments from running. Deleted the attachment and advised the user on safe email attachment practices.
#### Ticket #5: Internal Note
<img width="1160" height="679" alt="Spiceworks Internal Ticket Audit Note" src="https://github.com/user-attachments/assets/9580277e-cb35-41c2-94bc-3a25b47094b2" />


### Scenario 4: New-Hire Onboarding Request (Ticket #7)
- **The Issue:** HR requested accounts for 5 incoming employees ahead of orientation.
- **The Resolution:** Ran the account-creation script from my Active Directory lab (02_Create-CorporateStructure.ps1), which created the 5 accounts in the Corporate_Users OU of the CyberCorp.local domain, each with a temporary password and a forced password change at first logon.
#### Ticket #7: Internal Note and Public Comment
<img width="1151" height="803" alt="Screenshot 2026-11-06 at 7 18 07 PM" src="https://github.com/user-attachments/assets/bd4726f7-1517-4ef4-ac5d-e44a3afbd733" />


## Technical Skills Applied IT Service Management 
- **(ITSM) concepts**
- **Ticket triage and prioritization**
- **Help desk documentation (internal notes)**
- **Simulated multi-user ticket scenarios**
