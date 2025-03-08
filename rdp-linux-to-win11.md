# Connecting Linux Mint 22 Laptop to Windows 11 Pro Home PC via Remote Desktop

## Goal
Configure Windows 11 Pro on my home PC for Remote Desktop access, connect from my Linux Mint 22 Cinnamon laptop over the internet (e.g., coffee shops, libraries)—practice remote support skills.

## Setup
- Home PC: Windows 11 Pro, 64GB RAM, static IP 192.168.1.67
- Laptop: Linux Mint 22 Cinnamon, on public Wi-Fi
- Network: AT&T internet, BGW210-700 router (LAN: 192.168.1.0/24), VMs “PC1” (192.168.1.10) and “PC2” (192.168.1.11) on “MyNetwork”
- Tools: Windows Remote Desktop, Remmina (Linux RDP client), BGW210-700 port forwarding

## Steps
1. Enabled Remote Desktop on Windows 11 Pro (Home PC):
   - Configured with NLA and static IP 192.168.1.67.
2. Configured Port Forwarding on BGW210-700 Router:
   - Set RDP (Port 3389, TCP) to forward to 192.168.1.67, noted public IP.
3. Installed Remmina on Linux Mint 22 Cinnamon Laptop:
   - Added Remmina via package manager.
4. Connected from Linux Mint 22 to Windows 11 Pro:
   - Used Remmina to connect to [public IP]:3389 with “Personal Outlook Account.”
5. Tested VM Control:
   - Controlled “PC1” in VirtualBox remotely via RDP.

## Outcome
Linux Mint 22 laptop connects to Windows 11 Pro home PC via RDP from public Wi-Fi—remote access and VM control achieved!

## Screenshots
- ![RDP Setup](https://github.com/StandardBrian/IT-Projects/raw/images/rdp-win11-setup.png)
- ![Port Forwarding](https://github.com/StandardBrian/IT-Projects/raw/images/port-forwarding.png)
- ![Remmina Install](https://github.com/StandardBrian/IT-Projects/raw/images/remmina-install.png)
- ![RDP Connected](https://github.com/StandardBrian/IT-Projects/raw/images/rdp-connected.png)
- ![VM Control](https://github.com/StandardBrian/IT-Projects/raw/images/rdp-vm-control.png)

## Summary (Why I Did This)
- Practice remote desktop setup and networking—key help desk skills for supporting users remotely, leveraging A+ and Security+ knowledge.

## Notes (What I Learned)
- BGW210-700 NAT/Gaming forwards 3389 to 192.168.1.67—took ~30 min; dynamic IP might need dynamic DNS for stability.
