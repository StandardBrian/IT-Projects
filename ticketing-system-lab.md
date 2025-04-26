# Simulating a Ticketing System with osTicket in an AD Lab

## Goal
Install osTicket on “AD-Server” to simulate a help desk ticketing system, create and resolve mock user issues for “LabUser1”—practice ticket workflows and user communication.

## Setup
- Host: Windows 11 Pro, 64GB RAM, static IP 192.168.1.67
- VMs:
  - "AD-Server" (Windows Server 2025, 4GB RAM, 40GB disk, IP: 192.168.1.12, MAC: 08:00:27:BD:A3:74)
  - "PC1" (Windows 10, 4GB RAM, 40GB disk, IP: 192.168.1.10, MAC: 08:00:27:0E:41:0A)
  - "PC2" (Windows 10, 4GB RAM, 40GB disk, IP: 192.168.1.11, MAC: 08:00:27:C4:93:FB)
- Network: “MyNetwork” (Internal Network in VirtualBox)
- Tools: VirtualBox 7.0.12, osTicket (open-source ticketing system), Windows IIS, PHP 8.3.20, HeidiSQL, Microsoft Visual C++ Redistributable 2015-2022 (x64)

## Steps
1. Enabled IIS on “AD-Server”:
   - Server Manager > Manage > Add Roles and Features > Selected “Web Server (IIS)” with default features (HTTP, Static Content, Management Tools).
   - Installed IIS, confirmed `http://localhost` showed IIS welcome page.
2. Added CGI Feature for FastCGI Support:
   - Server Manager > Manage > Add Roles and Features > Expanded “Web Server (IIS)” > Web Server > Application Development > Checked “CGI.”
   - Installed CGI, restarted IIS to enable FastCGI for PHP.
3. Installed and Configured PHP:
   - Downloaded Non-Thread-Safe PHP 8.3.20 from windows.php.net, extracted to `C:\PHP`.
   - Copied `php.ini-development` to `php.ini`, enabled extensions (curl, gd, mbstring, openssl, pdo_mysql), added error logging (`log_errors = On`, `error_log = C:\PHP\php_errors.log`).
   - Installed Microsoft Visual C++ Redistributable 2015-2022 (x64) to resolve `VCRUNTIME140.dll` errors.
   - Registered PHP with IIS: Added Handler Mapping for `*.php` to `FastCgiModule` with `C:\PHP\php-cgi.exe`, set FastCGI settings (InstanceMaxRequests: 10000, PHP_FCGI_MAX_REQUESTS: 10000).
   - Tested PHP: Confirmed `http://localhost/test.php` showed PHP info page.
4. Installed osTicket:
   - Downloaded osTicket from osticket.com, extracted to a temporary location, then copied to `C:\inetpub\wwwroot\osTicket`.
   - Copied update file to `C:\inetpub\wwwroot\update`.
   - Renamed "update" to "osTicket"
   - Installed IIS URL Rewrite Module to support `web.config` rewrite rules.
   - Set permissions: Granted “IIS_IUSRS” Modify access to `C:\inetpub\wwwroot\osTicket` and `ost-config.php`.
   - Installed HeidiSQL for database management, configured database for osTicket.
   - Ran installer at `http://localhost/osTicket/`, configured admin account (username: “blongoria15,” email: `helpdesk@mylab.local`) and database.
5. Created Mock Tickets:
   - On “PC2”: Logged in as “LabUser1@mylab.local,” accessed `http://192.168.1.12/osTicket`.
   - Submitted ticket: “Can’t log in—password issue” (mock lockout).
   - Submitted second ticket: “Need access to Notepad++” (mock app request).
6. Resolved Tickets:
   - On “AD-Server”: Logged into osTicket admin panel as “blongoria15.”
   - Ticket 1: Reset “LabUser1” password in AD Users and Computers, replied: “Password reset to Temp123!@#—change at next login.”
   - Ticket 2: Installed Notepad++ on “PC2” (mock resolution), replied: “Notepad++ installed—available now.”
7. Tested:
   - On “PC2”: Logged in with new password, confirmed Notepad++—both issues resolved.

## Outcome
osTicket deployed on “AD-Server,” mock tickets created and resolved for “LabUser1”—simulated help desk workflow successfully!

## Screenshots
- ![osTicket Install](https://github.com/StandardBrian/IT-Projects/raw/images/osticket-install.png)
- ![Ticket Creation](https://github.com/StandardBrian/IT-Projects/raw/images/ticket-creation.png)
- ![Ticket Resolution](https://github.com/StandardBrian/IT-Projects/raw/images/ticket-resolution.png)

## Summary (Why I Did This)
- Practice help desk ticketing workflows—core A+ and help desk skill for managing user issues and communication.

## Notes (What I Learned)
- osTicket setup requires IIS with CGI, PHP 8.3.20, HeidiSQL, and Visual C++ Redistributable—troubleshooting `php.ini`, DLL errors, and IIS config took ~60 min; clear ticket replies cut user confusion, aligning with lockout prevention education.
