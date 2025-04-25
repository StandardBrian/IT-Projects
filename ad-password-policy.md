# Configuring Password Requirements in Active Directory

## Goal
Use Group Policy on “AD-Server” to enforce password requirements for “mylab.local” domain users—practice enterprise security management for help desk scenarios.

## Setup
- Host: Windows 11 Pro, 64GB RAM, static IP 192.168.1.67
- VMs:
  - "AD-Server" (Windows Server 2025, 4GB RAM, 40GB disk, IP: 192.168.1.12, MAC: 08:00:27:BD:A3:74)
  - "PC1" (Windows 10, 4GB RAM, 40GB disk, IP: 192.168.1.10, MAC: 08:00:27:0E:41:0A)
  - "PC2" (Windows 10, 4GB RAM, 40GB disk, IP: 192.168.1.11, MAC: 08:00:27:C4:93:FB)
- Network: “MyNetwork” (Internal Network in VirtualBox)
- Tools: VirtualBox 7.0.12, Windows Server Group Policy Management

## Steps
1. Configured Password Policy via Group Policy:
   - On “AD-Server”: Opened Group Policy Management (gpmc.msc).
   - Created new GPO “Password Policy” (There was already a Password Policy GPO I deleted it and added a new one).
   - Set Password Policy (Computer Configuration > Policies > Windows Settings > Security Settings > Account Policies > Password Policy):
     - Minimum Password Length: 12 characters.
     - Password Must Meet Complexity Requirements: Enabled (upper, lower, number, symbol).
     - Maximum Password Age: 90 days.
     - Minimum Password Age: 1 day.
   - Linked GPO to mylab.local, ran `gpupdate /force`.
2. Applied Policy to Domain Users:
   - Confirmed policy applied to “LabUser” via gpresult on “PC2.”
   - On “PC2”: Attempted weak password reset (e.g., “pass”)—rejected due to complexity rules.
3. Tested:
   - Set new complex password (e.g., “P@ssw0rd123!”) on “PC2”—accepted, logged in successfully.

## Outcome
Enforced strong password requirements for “mylab.local” users—enhanced domain security!

## Screenshots
- ![GPO Password Policy](https://github.com/StandardBrian/IT-Projects/raw/images/gpo-password-policy.png)
- ![GPO Apply](https://github.com/StandardBrian/IT-Projects/raw/images/gpo-apply.png)
- ![Password Rejection](https://github.com/StandardBrian/IT-Projects/raw/images/password-rejection.png)

## Summary (Why I Did This)
- Practice AD Group Policy for password security—key Security+ and help desk skill for user management and lockout prevention.

## Notes (What I Learned)
- GPO edit needed new policy due to permissions—12-char complex passwords took ~30 min; user education on strong passwords cuts lockouts.
