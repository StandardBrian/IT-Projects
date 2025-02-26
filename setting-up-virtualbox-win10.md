 Setting Up VirtualBox with Windows 11

## Goal
Deploy a Windows 10 VM on my Windows 11 PC using VirtualBox to create a help desk test environment.

## Setup
- **Host**: Windows 11 PC
- **Tools**: VirtualBox 7.x, Windows 10 ISO (trial version)
- **Specs**: 2GB RAM, 20GB dynamically allocated disk

## Steps
1. **Installed VirtualBox on Windows 11**  
   - Downloaded the Windows installer from virtualbox.org
   - Ran the .exe
   - Followed the setup wizard: Accepted defaults, allowed network adapter changes when prompted
   - Launched VirtualBox from Start menu to confirm it worked—no errors.

2. **Downloaded Windows 10 ISO**  
   - Visited microsoft.com/en-us/software-download/windows10 in Edge.
   - Used the Media Creation Tool: Clicked “Download tool now,” ran it, selected “Create installation media” > “ISO file” (not USB), chose Windows 10 64-bit.
   - Saved to Downloads folder.
   - Verified file wasn’t corrupt by checking its size matched expectations.

3. **Created a VM in VirtualBox**  
   - Opened VirtualBox, clicked “New” in the toolbar.
   - Named it “PC1,” set Type to “Microsoft Windows,” Version to “Windows 10 (64-bit).”
   - Allocated 4GB RAM
   - Created a virtual hard disk: Picked “Create a virtual hard disk now,” 20GB, VDI type, “Dynamically allocated” to save space.

4. **Configured Storage and Installed Windows 10**  
   - Went to Settings > Storage for “PC1”
   - Under “Controller: IDE,” clicked the empty disk icon, selected “Choose a disk file,” picked my Windows 10 ISO from Downloads.
   - Started the VM: Hit “Start,” saw the Windows boot screen, chose “Custom: Install Windows only” (no key needed for trial).
   - Followed install prompts: Picked the 20GB drive, waited ~30-60 minutes for install, set up a basic user account.

5. **Tested Functionality**  
   - Logged into Windows 10 VM, saw the desktop.
   - Opened Notepad (Start > type “Notepad”) and File Explorer to confirm it ran smoothly.
   - Shut down cleanly (Start > Power > Shut down) to avoid boot issues later.

## Outcome
Successfully set up a Windows 10 VM, ready for help desk troubleshooting scenarios.

## Screenshots
- ![VirtualBox on Win11](virtualbox-win11.png) *(Upload pending)*
- ![ISO Loaded](iso-loaded.png) *(Upload pending)*
- ![Windows 10 Desktop](win10-desktop.png) *(Upload pending)*

## Summary
- At this point the start of my virtual lab is ready. Virtual Machines are a great tool for learning you can experiment without messing with your physical device and they are inexpensive. I have also used the snapshot feature at the point of the first time logging in, this will make it
easier and much faster to make multiple machines.

## Notes
- Had an issue entering windows setup the first time booting. The first thing I tried doing was boot into the bios to change the boot order, but it kept giving me the same error. The way I fixed the problem was powering off the VM and disable the floppy disk drive completely.
