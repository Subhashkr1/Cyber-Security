Active scanning techniques involve interacting directly with the network or its components to gather information, identify vulnerabilities, or exploit targets. Unlike passive methods, active scanning sends data packets to the target network or device, which may trigger alerts on security systems.

Active Scanning Techniques
1. Ping Sweeping
Sends ICMP (Internet Control Message Protocol) echo requests to multiple hosts to check their availability.
Identifies live hosts and devices on a network.
Tools Used:
ping
nmap
Angry IP Scanner
2. Port Scanning
Identifies open ports and associated services running on a target system.
Determines vulnerabilities in network services (e.g., outdated software or misconfigurations).
Types of Port Scanning:
TCP Connect Scan: Completes the full TCP handshake for each port.
SYN Scan (Half-open scan): Sends SYN packets without completing the handshake (stealthier).
UDP Scan: Checks for open UDP ports by sending empty UDP packets.
XMAS Scan: Sends packets with specific flags (FIN, PSH, URG) to detect open or closed ports.
Tools Used:
nmap
Zenmap
Masscan
3. Vulnerability Scanning
Actively scans systems for known vulnerabilities, misconfigurations, or weak points in software or hardware.
Compares the target system against a database of known vulnerabilities (e.g., CVEs).
Tools Used:
Nessus
OpenVAS
QualysGuard
4. Network Mapping
Actively probes the network to map its topology, identify devices, and discover how they are connected.
Can reveal routers, switches, firewalls, and host systems.
Tools Used:
nmap
NetScanTools
SolarWinds Network Performance Monitor
5. OS Fingerprinting
Identifies the operating system of a target device by analyzing its response to specific probes.
Useful for understanding the target’s platform and potential vulnerabilities.
Techniques:
Active OS Fingerprinting: Sends custom packets to analyze TCP/IP stack behavior.
Passive OS Fingerprinting: Observes traffic without interacting.
Tools Used:
nmap
p0f
6. Service Enumeration
Gathers detailed information about running services on open ports (e.g., version, configuration).
Helps attackers identify exploitable services.
Examples:
Identifying a specific version of a web server (e.g., Apache 2.4.29).
Enumerating SMB shares, FTP banners, or HTTP headers.
Tools Used:
nmap with service detection (-sV)
Metasploit
Nikto
7. ARP Scanning
Sends ARP requests on the local network to discover active devices and their MAC addresses.
Often used to map devices in a subnet.
Tools Used:
arp-scan
NetDiscover
8. DNS Enumeration
Probes DNS servers to gather information about domain names, subdomains, and associated IPs.
Includes zone transfers, brute-forcing subdomains, and checking for misconfigurations.
Tools Used:
dnsenum
Dig
Fierce
9. Banner Grabbing
Captures and analyzes service banners to identify the software and version running on a system.
Helps detect vulnerabilities in outdated software.
Tools Used:
telnet
nc (netcat)
Nmap with banner grabbing scripts
10. WLAN Active Scanning
Actively probes wireless networks to gather information such as SSIDs, signal strength, and encryption types.
Used to identify weak or open wireless networks.
Tools Used:
Aircrack-ng Suite
Kismet
Wireshark
Precautions for Active Scanning
Authorization: Always obtain permission before scanning to avoid legal repercussions.
Stealth: Use stealthier methods (e.g., SYN scan) to evade detection.
Rate Limiting: Avoid overwhelming the network with excessive requests.
Monitoring: Be aware that active scanning can trigger alerts on intrusion detection/prevention systems (IDS/IPS).
