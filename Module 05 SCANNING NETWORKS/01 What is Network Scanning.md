# Network Scanning

## Introduction

Network scanning is a method used to identify active devices, services, and vulnerabilities within a network. It is a critical part of network security assessments and helps in mapping out the network infrastructure to uncover potential weaknesses that could be exploited.

## What is Network Scanning?

Network scanning involves using various tools and techniques to detect devices and services on a network. This process helps in creating a comprehensive view of the network and its security posture. Network scanning can be divided into several categories, including host discovery, port scanning, and service detection.

## Types of Network Scanning

### 1. **Host Discovery**

- **Description**: Identifying live hosts on a network. This step helps in determining which devices are active and reachable.
- **Tools**: [Nmap](https://nmap.org/), [Angry IP Scanner](https://angryip.org/)

### 2. **Port Scanning**

- **Description**: Detecting open ports on a device. Open ports can indicate available services and potential entry points for attacks.
- **Tools**: [Nmap](https://nmap.org/), [Netcat](https://nmap.org/ncat/)

### 3. **Service Detection**

- **Description**: Identifying services running on open ports. This includes determining the type and version of services, which helps in assessing vulnerabilities.
- **Tools**: [Nmap](https://nmap.org/), [Nikto](https://cirt.net/Nikto2)

### 4. **OS Fingerprinting**

- **Description**: Determining the operating system of a remote host. OS fingerprinting helps in understanding the target system's environment and potential vulnerabilities.
- **Tools**: [Nmap](https://nmap.org/), [p0f](http://lcamtuf.coredump.cx/p0f3/)

## Key Techniques

### 1. **Ping Sweep**

- **Description**: A method of determining which IP addresses in a range are active by sending ICMP Echo Requests.
- **Tools**: [Nmap](https://nmap.org/), [Fping](http://fping.org/)

### 2. **TCP Connect Scan**

- **Description**: Establishes a full TCP connection with the target port to determine if it is open.
- **Tools**: [Nmap](https://nmap.org/), [Netcat](https://nmap.org/ncat/)

### 3. **SYN Scan**

- **Description**: Sends SYN packets to ports and analyzes responses to determine if ports are open, closed, or filtered. This scan is stealthier than a TCP Connect Scan.
- **Tools**: [Nmap](https://nmap.org/)

### 4. **UDP Scan**

- **Description**: Scans for open UDP ports by sending UDP packets and observing responses or lack thereof.
- **Tools**: [Nmap](https://nmap.org/), [Netcat](https://nmap.org/ncat/)

## Common Tools for Network Scanning

- **[Nmap](https://nmap.org/)**: A versatile network scanning tool that supports various scanning techniques, including host discovery, port scanning, and service detection.
- **[Angry IP Scanner](https://angryip.org/)**: A lightweight tool for scanning IP addresses and ports.
- **[Netcat](https://nmap.org/ncat/)**: A networking utility for reading from and writing to network connections.
- **[Nikto](https://cirt.net/Nikto2)**: A web server scanner that performs service detection and vulnerability scanning.

## Best Practices

- **Authorization**: Ensure you have permission to scan the network. Unauthorized scanning can be illegal and unethical.
- **Avoid Overloading**: Be mindful of scan intensity to avoid overwhelming the network or devices.
- **Regular Scanning**: Conduct regular scans to keep track of changes in the network and new vulnerabilities.
- **Analysis**: Properly analyze scan results and prioritize remediation based on risk.

## Conclusion

Network scanning is an essential practice for identifying devices, services, and potential vulnerabilities within a network. By using appropriate tools and techniques, security professionals can gain valuable insights to enhance network security and mitigate risks.

## Resources

- [Nmap](https://nmap.org/)
- [Angry IP Scanner](https://angryip.org/)
- [Netcat](https://nmap.org/ncat/)
- [Nikto](https://cirt.net/Nikto2)

