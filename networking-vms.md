# Setting Up a Basic Network Between Two VMs

## Goal
Clone “PC1” into “PC2,” then network them to ping each other—practice help desk networking skills.

## Setup
- Host: Windows 11 PC
- VMs:
  - "PC1" (Windows 10, 4GB RAM, 20GB disk, MAC: 08:00:27:0E:41:0A)
  - "PC2" (Cloned from PC1—Windows 10, 4GB RAM, 20GB disk, MAC: 08:00:27:C4:93:FB)
- Tools: VirtualBox 7.0.12

## Steps
1. Cloned "PC1" to "PC2":
   - Right-clicked “PC1” in VirtualBox, cloned as “PC2” (full clone, current state).
   - Renamed “PC2” hostname via System Properties (sysdm.cpl); renamed user folder from “PC1” to “PC2” via temp admin user and registry edit (ProfileList).
2. Configured network:
   - Set “PC1” and “PC2” to “Internal Network” (named “MyNetwork”) in VirtualBox.
3. Assigned IPs:
   - “PC1”: 192.168.1.10, Subnet: 255.255.255.0
   - “PC2”: 192.168.1.11, Subnet: 255.255.255.0
4. Tested:
   - Pinged “PC2” (192.168.1.11) from “PC1”—got “Destination host unreachable”; cloned MAC (08:00:27:0E:41:0A) matched “PC1”; generated new MAC for “PC2” (08:00:27:C4:93:FB)—got replies.

## Outcome
“PC1” and “PC2” successfully networked—can ping each other.

## Screenshots
 ![PC2 Desktop](https://github.com/StandardBrian/IT-Projects/blob/images/pc2-desktop.png)
 ![PC1 IP Config](https://github.com/StandardBrian/IT-Projects/blob/images/ipconfig.png)
 ![Ping Success](https://github.com/StandardBrian/IT-Projects/blob/images/ping-success.png)
 ![PC2 Hostname](https://github.com/StandardBrian/IT-Projects/blob/images/pc2-hostname.png)

## Summary (Why I Did This)
- Wanted to practice networking—cloning and IP setup—for help desk troubleshooting with A+ skills.

## Notes (What I Learned)
- Cloning duplicated MAC (08:00:27:0E:41:0A) and user folder (“PC1”), breaking pings and clarity—new MAC (08:00:27:C4:93:FB), hostname “PC2,” and registry fix for user folder took ~20 min.
