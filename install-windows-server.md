# Installing Windows Server 2025 on a Virtual Machine

## Goal
Install Windows Server 2025 with Desktop Experience on a new VM to prepare for Active Directory—practice server setup for help desk and enterprise skills.

## Setup
- Host: Windows 11 Pro, 64GB RAM, static IP 192.168.1.67
- VM: “Server1” (Windows Server 2025, 4GB RAM, 50GB disk, IP: 192.168.1.12, MAC: 08:00:27:BD:A3:74)
- Network: “MyNetwork” (Internal Network in VirtualBox)
- Tools: VirtualBox 7.0.12, Windows Server 2025 ISO (trial from Microsoft Evaluation Center)

## Steps
1. Downloaded Windows Server 2025 ISO:
   - Obtained trial ISO from Microsoft Evaluation Center.
2. Created “Server1” VM:
   - VirtualBox > New > “AD-Server” Type: Microsoft Windows, Version: Windows Server 2022 (closest option), 4GB RAM, 40GB VDI (dynamic).
   - Attached ISO in Storage settings.
3. Installed Windows Server 2025:
   - Booted “Server1,” followed installer—chose Standard Edition with Desktop Experience, set admin password(P@$$w0rd123).
4. Configured Network:
   - Set static IP: 192.168.1.12, Subnet 255.255.255.0, Gateway blank (Internal Network), DNS 192.168.1.12 (self for AD later).
5. Tested:
   - Logged in, opened Server Manager—confirmed operational.

## Outcome
“AD-server” installed with Windows Server 2025 Desktop Experience—ready to host Active Directory!

## Screenshots
- ![ISO Attached](https://github.com/StandardBrian/IT-Projects/raw/images/iso-attached.png)
- ![Server Install](https://github.com/StandardBrian/IT-Projects/raw/images/server-install.png)
- ![Server Desktop](https://github.com/StandardBrian/IT-Projects/raw/images/server-desktop.png)

## Summary (Why I Did This)
- Practice server OS installation—foundation for AD and enterprise help desk skills with A+.

## Notes (What I Learned)
- Server 2025 trial lasts 180 days—took ~45 min; 40GB disk gives room for AD roles; VirtualBox lists 2022 but runs 2025 fine.
