DHCP Flooding
ChatGPT said:
ChatGPT
What is DHCP Flooding?
DHCP Flooding is a network attack where an attacker overwhelms a DHCP server by sending numerous fake DHCP discovery requests, aiming to exhaust the server’s pool of available IP addresses. This leads to a denial of service (DoS) for legitimate devices, preventing them from obtaining IP addresses and accessing the network.

How DHCP Flooding Works
DHCP Basics:

Dynamic Host Configuration Protocol (DHCP) dynamically assigns IP addresses to devices in a network.
It maintains a pool of available IP addresses for assignment.
Flooding the Server:

The attacker sends a flood of DHCP Discover packets using spoofed MAC addresses.
The DHCP server responds with offers and reserves IP addresses for the spoofed MAC addresses.
The pool of IP addresses is quickly exhausted.
Denial of Service:

Legitimate devices cannot obtain an IP address and are effectively disconnected from the network.
Motivations Behind DHCP Flooding
Network Disruption:

Attackers aim to cripple network services by preventing legitimate devices from connecting.
Facilitate MITM Attacks:

After flooding, attackers may introduce a rogue DHCP server to assign malicious configurations (e.g., attacker-controlled DNS servers).
Security Evasion:

Attackers use spoofed MAC addresses to bypass security systems that track device identities.
Tools for DHCP Flooding
Yersinia:

A powerful tool for DHCP attacks, including flooding and rogue server setup.
Command:
bash
Copy code
yersinia -G
dhcpstarv:

A dedicated DHCP starvation tool that floods the network with fake DHCP requests.
Ettercap:

Supports DHCP spoofing and flooding as part of its network attack capabilities.
Scapy:

A Python-based packet manipulation tool that can be scripted for DHCP flooding.
Impact of DHCP Flooding
Denial of Service (DoS):

Prevents legitimate devices from acquiring IP addresses.
Facilitates Rogue DHCP Attacks:

The attacker can introduce their own DHCP server to assign malicious network configurations.
Network Downtime:

Creates chaos in the network, impacting business operations or critical services.
Defenses Against DHCP Flooding
Enable DHCP Snooping:

Configure switches to identify trusted DHCP servers and block rogue or untrusted DHCP traffic.
Example (Cisco Switch):
bash
Copy code
ip dhcp snooping
ip dhcp snooping vlan <VLAN_ID>
ip dhcp snooping trust
Rate Limiting:

Limit the number of DHCP requests allowed per port or per second.
Port Security:

Restrict the number of MAC addresses per switch port to prevent the attacker from using multiple spoofed MAC addresses.
IP Address Allocation:

Use smaller DHCP scopes or static IP assignments for critical devices.
Rogue DHCP Detection:

Deploy tools or network monitoring systems to detect and block unauthorized DHCP servers.
Segmentation:

Isolate critical devices and servers on separate VLANs to minimize the attack surface.
Detection of DHCP Flooding
Unusual DHCP Logs:

Monitor the DHCP server logs for a high volume of Discover and Offer messages.
Network Monitoring:

Use tools like Wireshark to identify excessive DHCP traffic originating from a single device or with spoofed MAC addresses.
Switch Alerts:

Modern switches often log DHCP snooping or rate-limiting violations.
Advanced Mitigations
Static IP Addressing:

Assign static IPs to critical devices where possible to reduce reliance on DHCP.
Authentication with 802.1X:

Ensure only authenticated devices can connect to the network and request IP addresses.
Firewall Rules:

Limit DHCP traffic to specific devices or interfaces in the network.