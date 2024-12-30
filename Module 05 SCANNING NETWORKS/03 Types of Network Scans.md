# Types of Network Scans

## Introduction

Network scanning is a crucial aspect of network security assessments, used to discover active devices, open ports, services, and potential vulnerabilities. Different types of network scans serve various purposes and provide distinct insights into network security.

## Types of Network Scans

### 1. **Ping Sweep**

- **Description**: A ping sweep determines which IP addresses are active by sending ICMP Echo Requests to a range of IP addresses.
- **Purpose**: To identify live hosts on the network.
- **Tools**: [Nmap](https://nmap.org/), [Angry IP Scanner](https://angryip.org/)

### 2. **TCP Connect Scan**

- **Description**: Establishes a full TCP connection to the target port to check if it is open. This scan completes the TCP handshake.
- **Purpose**: To identify open TCP ports on a device.
- **Tools**: [Nmap](https://nmap.org/), [Netcat](https://nmap.org/ncat/)

### 3. **SYN Scan**

- **Description**: Sends SYN packets to target ports and analyzes the responses to determine the port status. This scan is also known as a "half-open" scan because it does not complete the TCP handshake.
- **Purpose**: To identify open ports without establishing a full connection, making it less detectable.
- **Tools**: [Nmap](https://nmap.org/)

### 4. **UDP Scan**

- **Description**: Sends UDP packets to target ports and observes the responses or lack thereof. Because UDP is connectionless, it can be more challenging to scan.
- **Purpose**: To detect open UDP ports and services.
- **Tools**: [Nmap](https://nmap.org/), [Netcat](https://nmap.org/ncat/)

### 5. **Service Detection**

- **Description**: Identifies services running on open ports and gathers information about their versions and configurations.
- **Purpose**: To assess the services running on devices and identify potential vulnerabilities.
- **Tools**: [Nmap](https://nmap.org/), [Nikto](https://cirt.net/Nikto2)

### 6. **OS Fingerprinting**

- **Description**: Determines the operating system of a remote host by analyzing responses to network packets.
- **Purpose**: To understand the target system's environment and potential vulnerabilities.
- **Techniques**:
  - **Active Fingerprinting**: Sends specially crafted packets to infer the OS.
  - **Passive Fingerprinting**: Analyzes traffic patterns and characteristics without actively probing.
- **Tools**: [Nmap](https://nmap.org/), [p0f](http://lcamtuf.coredump.cx/p0f3/)

### 7. **Idle Scan**

- **Description**: Uses a third-party "zombie" host to send packets to the target and infer the status of ports based on the responses. This scan is stealthy and can avoid detection.
- **Purpose**: To scan ports while avoiding detection.
- **Tools**: [Nmap](https://nmap.org/)

### 8. **FIN Scan**

- **Description**: Sends FIN packets to target ports. According to the TCP protocol, a closed port should respond with a RST packet, while an open port should ignore the FIN packet.
- **Purpose**: To identify open and closed ports in a stealthy manner.
- **Tools**: [Nmap](https://nmap.org/)

### 9. **Xmas Tree Scan**

- **Description**: Sends packets with the FIN, URG, and PSH flags set, making the packet appear like a Christmas tree with lit lights. It can reveal open and closed ports based on the responses.
- **Purpose**: To identify open and closed ports in a non-standard way.
- **Tools**: [Nmap](https://nmap.org/)

### 10. **NULL Scan**

- **Description**: Sends packets with no flags set. It is used to evade detection by sending minimal data to the target.
- **Purpose**: To discover open ports while avoiding detection.
- **Tools**: [Nmap](https://nmap.org/)

## Conclusion

Understanding different types of network scans is essential for effective network security assessments. Each scan type offers unique insights and has specific use cases, helping security professionals to thoroughly analyze and secure network environments.

## Resources

- [Nmap](https://nmap.org/)
- [Angry IP Scanner](https://angryip.org/)
- [Netcat](https://nmap.org/ncat/)
- [Nikto](https://cirt.net/Nikto2)
- [p0f](http://lcamtuf.coredump.cx/p0f3/)

