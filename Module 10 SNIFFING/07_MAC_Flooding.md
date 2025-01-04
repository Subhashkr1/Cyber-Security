What is MAC Flooding?
MAC Flooding is a network attack in which an attacker overwhelms a switch with fake MAC addresses, forcing it to act like a hub. The goal is to exploit the switch's MAC address table (also known as the CAM table), which stores MAC-to-port mappings for forwarding packets efficiently. When the table overflows, the switch enters a fail-open mode and broadcasts all incoming traffic to every port, enabling the attacker to intercept sensitive data.

How MAC Flooding Works
Switch Operation:

A switch maintains a MAC address table that maps devices' MAC addresses to specific switch ports.
This table has limited storage capacity.
Flooding the Table:

The attacker sends a massive number of packets with random, spoofed source MAC addresses.
The table becomes full and cannot store new legitimate entries.
Broadcast Mode:

In fail-open mode, the switch broadcasts packets to all ports because it cannot determine the correct destination port.
Data Interception:

The attacker’s device captures the broadcast traffic, including sensitive data such as credentials, emails, or other unencrypted information.
Motivations Behind MAC Flooding
Eavesdropping: Capturing sensitive traffic on a switched network.
MITM Attacks: Intercepting and modifying data in real time.
Disruption: Causing network instability or degraded performance.
Security Bypass: Exploiting network vulnerabilities for further attacks.
Tools Used for MAC Flooding
macof (part of dsniff suite):

Generates a flood of packets with random MAC addresses to fill the MAC table.
Command:
bash
Copy code
macof -i <interface>
Yersinia:

A versatile network attack tool that supports MAC flooding and other switch-based attacks.
Command:
bash
Copy code
yersinia -I
Ettercap:

A network sniffing and MITM attack tool with support for MAC table attacks.
Scapy:

A Python-based tool that can be scripted to generate packets with spoofed MAC addresses.
Steps to Perform MAC Flooding
Identify the Target Switch:
Use tools like Nmap or arp-scan to map the network.
Send Flood of Packets:
Use a tool like macof to generate packets with random MAC addresses.
Capture Broadcast Traffic:
Use a packet capture tool (e.g., Wireshark) to intercept the broadcasted traffic.
Analyze Captured Data:
Extract sensitive information from the captured packets.
Impact of MAC Flooding
Confidentiality:
Allows attackers to eavesdrop on sensitive network traffic.
Performance:
Degrades network performance due to excessive broadcasting.
Service Disruption:
May lead to denial-of-service (DoS) conditions for legitimate users.
Defenses Against MAC Flooding
Port Security:

Limit the number of MAC addresses that can be learned on a switch port.
Example (Cisco Switch):
bash
Copy code
switchport port-security
switchport port-security maximum 2
switchport port-security violation shutdown
Dynamic ARP Inspection (DAI):

Monitors ARP traffic and validates MAC-to-IP mappings against a trusted database.
MAC Address Table Aging:

Regularly clears unused MAC addresses to prevent table overflows.
Network Monitoring:

Use tools like SNMP or syslog to detect unusual MAC address activity.
VLAN Segmentation:

Isolate sensitive traffic on separate VLANs to reduce exposure.
Intrusion Detection Systems (IDS):

Deploy IDS/IPS solutions to detect and block MAC flooding attempts.
Quality Switches:

Use enterprise-grade switches with robust security features like flood protection or dedicated buffer management.
Detection of MAC Flooding
Unusual Network Behavior:

High CPU utilization on switches.
Sudden broadcast storms on the network.
Logs and Alerts:

Monitor switch logs for warnings about CAM table overflows.
Packet Analysis:

Tools like Wireshark can reveal excessive traffic with randomized MAC addresses.