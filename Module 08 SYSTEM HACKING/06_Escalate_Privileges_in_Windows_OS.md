Privilege escalation in Windows OS involves exploiting system vulnerabilities, misconfigurations, or weak security settings to gain higher-level permissions, such as administrative or SYSTEM privileges. Ethical hackers or penetration testers perform this step to identify security flaws, while attackers may use it for malicious purposes.

Types of Privilege Escalation
Vertical Privilege Escalation: Gaining higher privileges, such as administrative rights.
Horizontal Privilege Escalation: Accessing the privileges of another user with the same level.
Techniques for Privilege Escalation in Windows
1. Exploiting Unpatched Vulnerabilities
Use vulnerabilities in the Windows OS or applications to escalate privileges.
Example: EternalBlue or PrintNightmare exploits.
Tools:
Metasploit Framework: For automated exploitation.
Exploit-DB: To find suitable exploits.
Example command in Metasploit:
bash
Copy code
use exploit/windows/local/printnightmare
2. Exploiting Weak File or Folder Permissions
Files and directories with insecure permissions can allow modification or replacement of executables.

Check Permissions:

bash
Copy code
icacls C:\path\to\file
Look for Everyone or Authenticated Users with full control.

3. DLL Hijacking
If an application loads DLLs without specifying a full path, attackers can place malicious DLLs in the search directories.

Steps:
Identify vulnerable applications.
Create a malicious DLL.
Place it in the required directory.
Tools:
Process Monitor (Procmon): To monitor DLL loading.
4. Unquoted Service Path
Windows services with unquoted paths can be exploited if the path contains spaces.

Steps:
Identify services with unquoted paths:

bash
Copy code
wmic service get name,displayname,pathname,startmode | findstr /i "auto" | findstr /i /v "C:\Windows\"
Place a malicious executable in the path.

5. Insecure Registry Permissions
Registry keys with weak permissions can allow privilege escalation.

Steps:
Identify keys with weak permissions:

bash
Copy code
reg query HKLM /s /t REG_SZ | findstr "YOUR_TARGET_KEY"
Exploit the key by modifying it to execute malicious code.

6. Bypassing User Account Control (UAC)
UAC bypass can elevate privileges without user interaction.

Techniques:
Hijack auto-elevating programs.
Modify HKCU\Software\Classes registry keys.
Tools:
PowerSploit: Automates UAC bypass.
7. Token Impersonation
In Windows, tokens represent user permissions. If an attacker can impersonate a higher-privileged token, they can escalate privileges.

Steps:
Check for available tokens:

bash
Copy code
whoami /priv
Impersonate tokens using tools like Incognito or Metasploit.

8. Scheduled Tasks
Misconfigured or vulnerable scheduled tasks can be exploited to execute malicious code with elevated privileges.

Steps:
Identify tasks:

bash
Copy code
schtasks /query /fo LIST /v
Modify or replace the executable associated with the task.

9. Exploiting SAM and SYSTEM Files
These files store sensitive information, including hashed passwords.

Steps:
Copy SAM and SYSTEM files:

bash
Copy code
copy C:\Windows\System32\config\SAM .
copy C:\Windows\System32\config\SYSTEM .
Extract hashed passwords using tools like Mimikatz or pwdump.

10. Exploiting Legacy Protocols
Older protocols, such as SMBv1, can be vulnerable to attacks.

Example: Exploiting SMB shares with tools like EternalBlue.
11. Windows Kernel Exploits
Kernel vulnerabilities can be used to gain SYSTEM privileges.

Example Exploit:
CVE-2021-1675 (PrintNightmare): Allows remote code execution and privilege escalation.
Tools:
Windows Exploit Suggester: Suggests exploits based on system information.
Metasploit:
bash
Copy code
use exploit/windows/local/ms10_092_schelevator
Common Tools for Privilege Escalation
PowerSploit: PowerShell scripts for exploitation.
Mimikatz: For credential dumping and token manipulation.
Windows Exploit Suggester: Matches system details with available exploits.
Metasploit Framework: Automates the exploitation process.
SharpHound + BloodHound: Maps AD privileges to find attack paths.
Procmon: Monitors processes and file permissions.
Prevention and Mitigation
Keep Systems Updated: Apply patches regularly.
Minimize Permissions: Follow the principle of least privilege.
Secure File and Registry Permissions: Remove unnecessary access.
Enable Logging and Monitoring: Track suspicious activity.
Disable Legacy Protocols: SMBv1, Telnet, and similar insecure services.