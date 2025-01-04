How to Set Up a DHCP Rogue Server (MITM Attack)
A DHCP Rogue Server is a malicious DHCP server set up by an attacker to provide invalid or malicious network configuration to clients. When a legitimate DHCP server exists in the network, the rogue server can trick devices into using incorrect settings, such as a malicious DNS server or gateway, enabling the attacker to intercept traffic, redirect it, or perform other attacks.

Below is a step-by-step guide on setting up a DHCP Rogue Server in a man-in-the-middle (MITM) attack.

Prerequisites
Attacker's Machine: Should have a tool to set up the rogue DHCP server (such as Yersinia, dnsmasq, or Ettercap).
Target Network: The network where the legitimate DHCP server is operating.
Privilege Level: Root/Administrator access on the attacker’s machine to run the necessary tools.
Tools for Setting Up a Rogue DHCP Server
Yersinia (popular network attack tool)
dnsmasq (DHCP and DNS forwarding service)
Ettercap (MITM attack tool)
Scapy (Python tool for packet crafting)
Step 1: Setting Up the Rogue DHCP Server Using Yersinia
Yersinia is a powerful tool that can create a rogue DHCP server and perform various attacks.

Install Yersinia:
On Linux:
bash
Copy code
sudo apt-get install yersinia
Run Yersinia for DHCP Rogue Attack:
Start Yersinia in graphical mode:
bash
Copy code
sudo yersinia -G
Once the interface opens, select DHCP from the attack types.
Choose Rogue DHCP Server and launch the attack.
Yersinia will begin sending DHCP offers to devices on the network, acting as a rogue server.
Step 2: Using dnsmasq to Set Up a Rogue DHCP Server
dnsmasq is a lightweight DNS and DHCP server used to set up a rogue server.

Install dnsmasq:
On Linux:
bash
Copy code
sudo apt-get install dnsmasq
Configuration:
Create a configuration file for dnsmasq (e.g., /etc/dnsmasq.conf).

Example configuration:

bash
Copy code
# Rogue DHCP server
dhcp-range=192.168.1.50,192.168.1.100,12h
dhcp-option=3,192.168.1.1       # Gateway (can be your attacking machine)
dhcp-option=6,192.168.1.1       # DNS (can be your attacking machine)
In this configuration:

dhcp-range: The IP address pool that the rogue server will offer.
dhcp-option 3: The gateway that the devices will use (attacker's machine).
dhcp-option 6: The DNS server (attacker’s machine).
Start dnsmasq with the configuration file:

bash
Copy code
sudo dnsmasq -C /etc/dnsmasq.conf
This will start the rogue DHCP server on your machine.

Step 3: Using Ettercap for MITM Attack
Ettercap is a tool that can intercept traffic between a victim and the network. It can also be used to perform a rogue DHCP attack.

Install Ettercap:
On Linux:
bash
Copy code
sudo apt-get install ettercap-text-only
Run Ettercap:
Start Ettercap in text mode:

bash
Copy code
sudo ettercap -T -q -i eth0 -M arp:remote /target_ip/ /gateway_ip/
eth0: The network interface to use.
/target_ip/: The victim’s IP address.
/gateway_ip/: The IP address of the default gateway.
Start the MITM attack, and Ettercap will begin poisoning the ARP cache of the target device and the gateway.

Once the MITM is set up, you can proceed with the rogue DHCP setup to give out malicious IP configurations.

Step 4: Targeting Devices with the Rogue Server
Once the rogue DHCP server is active, it will start offering IP addresses and configuration information (such as DNS and gateway settings) to the devices on the network. These devices will attempt to connect to the network and use the attacker's settings for communication.

Devices on the network will receive IP addresses and settings from the rogue DHCP server.
The attacker can then manipulate these devices' network traffic, such as redirecting them to phishing sites, intercepting data, or launching further attacks.
Step 5: Testing the Rogue DHCP Server
On a target device, run the following command to check the assigned IP:

bash
Copy code
ifconfig
Confirm the IP, gateway, and DNS server IP match the attacker's configuration.
You can also use Wireshark to monitor DHCP traffic and verify that the rogue DHCP server is sending responses.

Defenses Against Rogue DHCP Servers
DHCP Snooping:

Enable DHCP snooping on switches to ensure that only trusted DHCP servers can respond.
Static IP Addressing:

Set critical systems to use static IP addresses, avoiding DHCP-based attacks.
Network Monitoring:

Use intrusion detection systems (IDS) or network monitoring tools to detect rogue DHCP servers.
Port Security:

Restrict devices that can connect to the network using MAC address filtering.
802.1X Authentication:

Require devices to authenticate before gaining access to the network, limiting rogue server access.
Important Considerations
Legality: DHCP Rogue Server attacks are illegal if performed on networks without explicit permission. Always ensure you have proper authorization before performing any testing.
Impact: This type of attack can severely disrupt a network by isolating devices and performing MITM attacks, so it is essential to use proper defenses.