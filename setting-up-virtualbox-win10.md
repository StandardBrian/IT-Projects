This is something I am very familiar with doing. I used Virtual Machines in college to complete assigns. Although they are not very complicated to understand I think its valuable to demonstrate I know the technology because it is used in many networks to cut cost of physical machines.

Install VirtualBox
  Step 1: Visit https://www.virtualbox.org/wiki/Downloads and download the version of virtual box for my OS.
    - In this case windows 
  Step 2: Run the .exe file, and follow the setup wizard
  Step 3: Open VirtualBox and verify it is working
  Step 4: Restart PC

Create Windows ISO file
  Step 1: Visit https://www.microsoft.com/en-us/software-download/windows10 and download the windows media creation tool
  Step 2: Run .exe file just downloaded and navigate through the set up
    - Make sure not to pick the option to download windows 10 to a bootable device or ISO file
  
Setting Up Windows 10 VM
  Step 1: Click "New" to make new VM.
  Step 2: Name the VM and Select the Windows ISO file.
  Step 3: Allocate VM resorces from my physical machine
    - Memory 4GB
    - Cores 1
    - HDD 20 GB
    - Network Adapter enable
  Step 4: Start VM and complete windows setup
    - Windows 10 Pro
  Step 5: Restart VM and Sign into windows to verify completion

Summary:
At this point the start of my virtual lab is ready. Virtual Machines are a great tool for learning you can experiment without messing with your physical device and they are inexpensive. I have also used the snapshot feature at the point of the first time logging in, this will make it
easier and much faster to make multiple machines.

Notes: 
- Had an issue entering windows setup the first time booting. The first thing I tried doing was boot into the bios to change the boot order, but it kept giving me the same error. The way I fixed the problem was powering off the VM and disable the floppy disk drive completely.

# Setting Up VirtualBox with Windows 10 on Windows 11

## Goal
Deploy a Windows 10 VM on my Windows 11 PC using VirtualBox to create a help desk test environment.

## Setup
- **Host**: Windows 11 PC
- **Tools**: VirtualBox 7.x, Windows 10 ISO (trial version)
- **Specs**: 2GB RAM, 20GB dynamically allocated disk

## Steps
1. Installed VirtualBox on Windows 11 from official site.
2. Downloaded Windows 10 ISO using Microsoft’s Media Creation Tool.
3. Created a VM in VirtualBox named "HelpDeskTest" (Windows 10, 64-bit).
4. Configured Storage to load the ISO, started VM, and installed Windows 10.
5. Tested functionality by logging in and launching Notepad.

## Outcome
Successfully set up a Windows 10 VM, ready for help desk troubleshooting scenarios (e.g., no-boot fix next).

## Screenshots
- ![VirtualBox on Win11](virtualbox-win11.png) *(Upload pending)*
- ![ISO Loaded](iso-loaded.png) *(Upload pending)*
- ![Windows 10 Desktop](win10-desktop.png) *(Upload pending)*
