# DoS in Networking

A **Denial of Service (DoS)** attack in networking involves exploiting vulnerabilities in network protocols, services, or configurations to disrupt the normal functioning of a target system or network. Tools like **hping3**, **Metasploit Framework (MSF)**, and **Yersinia** are commonly used for performing or simulating DoS attacks.

---

## 1. **hping3**

### Overview:
**hping3** is a command-line packet crafting tool used for testing, scanning, and simulating DoS attacks. It allows users to generate custom packets and send them to a target, making it a powerful tool for network diagnostics and security testing.

### Key Features:
- Supports TCP, UDP, ICMP, and raw IP protocols.
- Allows custom packet crafting (e.g., source IP spoofing, payload customization).
- Can simulate attacks like SYN floods and UDP floods.

### Example Commands:
- **SYN Flood**:
  ```bash
  hping3 -S --flood -p 80 <target_ip>
  ```
 Sends a flood of SYN packets to the target's port 80.

 UDP Flood:
  ```bash 
  hping3 --udp --flood -p 53 <target_ip>
  ```
  Sends a flood of UDP packets to port 53 (commonly DNS).

## 2. **Metasploit Framework (MSF)**
Overview:
The Metasploit Framework is a powerful penetration testing platform that includes modules for simulating DoS attacks. It automates the process of exploiting vulnerabilities in network services to cause disruption.

### Key Features:
- Comprehensive library of exploits and payloads.
- Modules specifically designed for DoS testing.
- Supports customization and chaining of attacks.

### Example Usage:
- **Search for a DoS Module**:
```bash
search dos
```
Select and Configure a Module:
```bash
use auxiliary/dos/tcp/synflood
set RHOST <target_ip>
set RPORT <target_port>
run
```
Run the DoS Attack: Executes the selected DoS module on the specified target.

## **3. Yersinia**
Overview:
Yersinia is a tool designed to exploit vulnerabilities in Layer 2 network protocols. It is particularly effective for targeting switches, routers, and other network devices in a Local Area Network (LAN).

- Supported Protocols:
- Spanning Tree Protocol (STP)
- Cisco Discovery Protocol (CDP)
- Dynamic Trunking Protocol (DTP)
- VLAN Trunking Protocol (VTP)
- Hot Standby Router Protocol (HSRP)

### Example Commands:
Launch Yersinia Interactive Mode:
```bash
yersinia -I
```
Select a Protocol Attack:
In the interactive mode, select the protocol (e.g., STP, DTP) and execute the attack.
Automated Attack:
```bash
yersinia -G
```
Launches a graphical interface for easier attack selection and execution.
Comparison of Tools
Tool	Purpose	Protocols	Example Attacks

hping3	Packet crafting and testing	TCP, UDP, ICMP	SYN flood, UDP flood
MSF	Penetration testing and exploitation	Multiple	SYN flood, application-level DoS
Yersinia	Layer 2 protocol exploitation	STP, CDP, DTP, VTP	STP root bridge attack, VLAN hopping
Ethical Considerations
The use of these tools without explicit permission is illegal and unethical.
They should only be used in controlled environments for security testing or research purposes.
Mitigation Strategies

hping3 Attacks:

Implement rate-limiting on critical services.
Use intrusion detection systems (IDS) to detect and block abnormal traffic.
MSF Attacks:
Regularly patch and update software to fix vulnerabilities.
Use firewalls and monitoring tools to detect exploitation attempts.

Yersinia Attacks:
Secure Layer 2 protocols by disabling unnecessary services (e.g., CDP).
Implement VLAN segmentation and use 802.1X for port security.