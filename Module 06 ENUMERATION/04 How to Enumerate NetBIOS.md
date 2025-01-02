# How to Enumerate NetBIOS

NetBIOS (Network Basic Input/Output System) is used for network communication in Windows environments. Enumerating NetBIOS information involves discovering network resources and services using various tools and techniques. Below are methods for enumerating NetBIOS.

## Methods for Enumerating NetBIOS

### 1. Using Nmap

Nmap is a powerful network scanning tool that can be used to enumerate NetBIOS information.

#### Command

```bash
nmap -p 137 --script nbstat <target>
```

Description

-p 137: Specifies the NetBIOS Name Service (NBNS) port.

--script nbstat: Uses the nbstat script to gather NetBIOS names and information.

### 2. Using NetBIOS Enumeration Tools
Several tools are designed specifically for NetBIOS enumeration.

nbtscan
nbtscan is a network scanner that can discover NetBIOS names and IP addresses.

Command
```bash
nbtscan <network-range>
```
Example
```bash
nbtscan 192.168.1.0/24
```

Nbtstat

nbtstat is a command-line tool in Windows for displaying NetBIOS over TCP/IP (NetBT) statistics.

Commands
To display the NetBIOS name table of a remote system:

```cmd
nbtstat -A <IP-address>
```

Example:

```cmd
nbtstat -A 192.168.1.10
```
To display the local NetBIOS name table:

cmd
nbtstat -n
### 3. Using Metasploit
Metasploit is a penetration testing framework with modules for NetBIOS enumeration.

Commands
Load the module:

```bash
use auxiliary/scanner/netbios/nbname
Set the target and run the module:
```
```bash
set RHOSTS <target>
run
```

### 4. Using Python Scripts
Custom Python scripts can be used to enumerate NetBIOS information.

Example Script

```python

import socket

def query_netbios(ip):
    try:
        # Create a UDP socket
        sock = socket.socket(socket.AF_INET, socket.SOCK_DGRAM)
        sock.settimeout(2)
        
        # Send a NetBIOS Name Service query
        query = b'\x81\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00\x00'
        sock.sendto(query, (ip, 137))
        
        # Receive response
        response, _ = sock.recvfrom(1024)
        print(response)
        
    except socket.error as e:
        print(f"Socket error: {e}")
```

## Example usage
query_netbios('192.168.1.10')

**Conclusion**

Enumerating NetBIOS can help identify network resources and services. Using tools such as Nmap, nbtscan, nbtstat, Metasploit, and custom scripts allows for effective NetBIOS enumeration. Always ensure to perform these activities with proper authorization and in accordance with network policies.