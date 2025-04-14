# Setting Up an Active Directory Server in a Virtual Lab

## Goal
Promote “AD-Server” to an Active Directory Domain Controller and join “PC1” and “PC2” to the domain—expand my lab with centralized user management.

## Setup
- Host: Windows 11 Pro, 64GB RAM, static IP 192.168.1.67
- VMs:
  - "Server1" (Windows Server 2025, 4GB RAM, 40GB disk, IP: 192.168.1.12, MAC: 08:00:27:BD:A3:74)
  - "PC1" (Windows 10, 4GB RAM, 40GB disk, IP: 192.168.1.10, MAC: 08:00:27:0E:41:0A)
  - "PC2" (Windows 10, 4GB RAM, 40GB disk, IP: 192.168.1.11, MAC: 08:00:27:C4:93:FB)
- Network: “MyNetwork” (Internal Network in VirtualBox)
- Tools: VirtualBox 7.0.12, Windows Server AD DS

## Steps
1. Promoted “Server1” to Domain Controller:
   - Server Manager > Add Roles and Features > Installed Active Directory Domain Services (AD DS).
   - Promoted to DC: Configured new domain “mylab.local,” set DNS to 192.168.1.12.
2. Joined “PC1” and “PC2” to the Domain:
   - Updated DNS on both to 192.168.1.12 (Control Panel > Network > IPv4).
   - System Properties > Changed to domain “mylab.local,” authenticated with “Administrator@mylab.local.”
3. Tested Domain Functionality:
   - Created user “LabUser” in AD Users and Computers on “Server1.”
   - Logged into “PC2” with “LabUser@mylab.local”—successful login.

## Outcome
“Server1” runs as an Active Directory Domain Controller, “PC1” and “PC2” joined “mylab.local”—centralized lab management achieved!

## Screenshots
- ![AD Setup](https://github.com/StandardBrian/IT-Projects/blob/images/active-directory-installed.png)
- ![Created Users On AD Server](https://github.com/StandardBrian/IT-Projects/blob/images/created-users.png)
- ![User Connected to Domain](https://github.com/StandardBrian/IT-Projects/blob/images/connected-to-domain.png)

## Summary (Why I Did This)
- Practice Active Directory setup and domain management—key help desk and enterprise skills with A+ foundations.

## Notes (What I Learned)
- AD needs DNS on the DC—took ~40 min; “mylab.local” keeps it simple for a lab.
