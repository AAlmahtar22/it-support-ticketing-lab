# IT Support Operations & Ticket Lifecycle Lab (Spiceworks Cloud)

## Project Overview
This project simulates real-world IT Support Desk operations within a sandboxed corporate environment (Almahtar IT Services). By configuring a cloud-hosted ITSM platform, this lab demonstrates foundational help desk skills: ticket triage, incident categorization, user communication, and operational documentation. 

Instead of basic troubleshooting, the tickets logged here directly audit the infrastructure, networking, and security policies configured in my other engineering environments.

## Core Configurations
- **Custom Service Desk Architecture:** Implemented structured ticket routing categories to bucket incoming issues under Identity Management (AD), Network Connectivity, and Endpoint Hardening (GPO).
- **Multi-User Simulation:** Simulated tickets logged by distinct non-technical cross-departmental users utilizing Spiceworks backend email parsing overrides (`#created by`).
- **Knowledge Management:** Documented detailed internal engineering logs within closed ticket timelines to establish historical auditing records and streamline cross-team knowledge transfers.

## Documented Support Scenarios

### Scenario 1: Identity & Access Management (AD) Escalation
- **The Issue:** A Tier 1 administrator account was blocked when attempting to log into a high-security Tier 0 Domain Controller terminal.
- **The Resolution:** Verified the system event logs. Confirmed the block was expected behavior under the tiered admin account structure from my Active Directory lab, which keeps Tier 1 (server) admin accounts separate from Tier 0 (domain) systems to limit how far a compromised account can reach. Documented the approved way to manage the domain controller remotely using Remote Server Administration Tools (RSAT).

### Scenario 2: Network & Subnet Connectivity Boundary
- **The Issue:** An HR end-user reported being unable to connect or print to an asset physically located inside the Finance department office network.
- **The Resolution:** Traced the connection timeout to the VLAN separation between departments. Confirmed network traffic isolation across distinct department subnets (HR: VLAN 10, Finance: VLAN 20) configured on a Cisco Catalyst 2960 switch to limit broadcast domains.

### Scenario 3: Endpoint Security & Malware Mitigation Block
- **The Issue:** An executive assistant reported a system-level policy block when attempting to launch a vendor billing script attachment (`Invoice_Archive.vbs`) received via email.
- **The Resolution:** Identified the attachment as a high-risk security threat. Documented that the execution loop was successfully caught and dropped by our active Group Policy baseline restricting Windows Script Host (`wscript.exe`) endpoints to block email-borne ransomware.
<img width="1160" height="679" alt="Screenshot 2026-11-03 at 10 08 45 PM" src="https://github.com/user-attachments/assets/9580277e-cb35-41c2-94bc-3a25b47094b2" />
<img width="1160" height="679" alt="Screenshot 2026-11-03 at 10 03 30 PM" src="https://github.com/user-attachments/assets/f5f6875d-f3d9-4ba8-9bab-a9ef3276c7e4" />

---

## Technical Skills Applied
- IT Service Management (ITSM) / ITIL Frameworks
- Ticket Lifecycle Triage & Prioritization Matrices
- Technical Help Desk Documentation (Internal Notes)
- Multi-User Escalation Workflows
