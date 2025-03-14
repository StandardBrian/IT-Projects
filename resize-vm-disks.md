# Resizing Virtual Hard Disks for PC1 and PC2 to 40GB

## Goal
Resize the virtual hard disks of “PC1” and “PC2” from 20GB to 40GB—practice disk management and backup for help desk scenarios.

## Setup
- Host: Windows 11 Pro, 64GB RAM, static IP 192.168.1.67
- VMs:
  - "PC1" (Windows 10, 4GB RAM, resized to 40GB disk, IP: 192.168.1.10, MAC: 08:00:27:0E:41:0A)
  - "PC2" (Windows 10, 4GB RAM, resized to 40GB disk, IP: 192.168.1.11, MAC: 08:00:27:C4:93:FB)
- Network: “MyNetwork” (Internal Network in VirtualBox)
- Tools: VirtualBox 7.0.12, Windows Disk Management

## Steps
1. Resized Disks in VirtualBox:
   - Shut down “PC1” and “PC2” in VirtualBox.
   - VirtualBox > “PC1” > Settings > Storage > Resized VDI from 20GB to 40GB; repeated for “PC2.”
2. Backed Up Hard Drives:
   - Copied “PC1.vdi” and “PC2.vdi” to backup folder on host (e.g., C:\Backups).
3. Extended C: Drives:
   - Disk Management (Win + R > `diskmgmt.msc`) > Right-clicked C: > “Extend Volume” > Used full 40GB space—repeated for “PC2.”
4. Tested:
   - File Explorer on both VMs—confirmed C: drives at 40GB, wrote test files.

## Outcome
“PC1” and “PC2” virtual hard disks resized to 40GB, C: drives extended—expanded storage achieved!

## Screenshots
- ![VirtualBox Resize](https://github.com/StandardBrian/IT-Projects/raw/images/vbox-resize.png)
- ![Backup Copy](https://github.com/StandardBrian/IT-Projects/raw/images/backup-copy.png)
- ![Extended Volume](https://github.com/StandardBrian/IT-Projects/raw/images/extended-volume.png)

## Summary (Why I Did This)
- Practice disk resizing and management—core A+ help desk skills for storage upgrades.

## Notes (What I Learned)
- VirtualBox resize with Disk Management extension worked—took ~25 min per VM; backups ensured safety, recovery partitions left intact.
