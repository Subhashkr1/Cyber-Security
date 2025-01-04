Sniffing can be broadly categorized into passive sniffing and active sniffing, based on the methods used and the network environment. Each type targets capturing and analyzing network traffic but employs different techniques depending on the infrastructure.

1. Passive Sniffing
Involves listening to and capturing data packets on a network without injecting or altering traffic.
Typically used on non-switched networks, such as those using hubs, where all devices receive every packet.
Characteristics:
Non-intrusive: Does not interfere with network traffic.
Harder to detect: Operates silently, making it stealthy.
Primarily captures broadcast and unicast traffic meant for other devices.
Common Use Cases:
Monitoring network performance.
Analyzing unencrypted data, such as plain-text passwords.
Tools:
Wireshark
tcpdump
2. Active Sniffing
Involves injecting or manipulating traffic to capture data in networks that use switches.
Switches forward packets only to the intended recipient, so active methods are required to bypass this restriction.
Characteristics:
Intrusive: Actively interacts with the network, potentially altering its state.
Detectable: May trigger alerts on intrusion detection systems (IDS).
Techniques:
ARP Spoofing/Poisoning:

Manipulates the ARP tables to associate the attacker’s MAC address with the IP of a legitimate device.
Redirects traffic through the attacker’s system.
MAC Flooding:

Overwhelms a switch's MAC address table with fake entries, causing it to function as a hub.
Enables capturing traffic meant for other devices.
DNS Spoofing:

Redirects DNS requests to malicious servers, capturing sensitive data like credentials.
DHCP Spoofing:

Provides a rogue DHCP server to assign malicious configurations, enabling man-in-the-middle (MITM) attacks.
Port Mirroring:

Configures the switch to send copies of network traffic to a specific port for sniffing.
Tools:
Ettercap
Cain and Abel
dsniff
Comparison of Passive and Active Sniffing
Aspect	Passive Sniffing	Active Sniffing
Environment	Non-switched networks (hubs)	Switched networks (switches)
Intrusiveness	Non-intrusive	Intrusive
Detection	Harder to detect	Easier to detect
Techniques	Captures broadcast traffic	ARP spoofing, MAC flooding, etc.
Types of Data Captured Through Sniffing
Plain-text communication: Unencrypted protocols (e.g., HTTP, FTP, Telnet).
Login credentials: Usernames and passwords.
Session tokens: Used for session hijacking.
