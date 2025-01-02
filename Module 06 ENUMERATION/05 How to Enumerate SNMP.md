# SNMP Enumeration Guide

Enumerating SNMP (Simple Network Management Protocol) typically involves gathering information from network devices using SNMP queries. This process is commonly used in network management and security testing to collect details like system descriptions, interfaces, IP addresses, routing tables, and more.

## Steps to Enumerate SNMP

### 1. Identify SNMP Version
- SNMP has three versions: v1, v2c, and v3.
- v1 and v2c use community strings for authentication.
- v3 provides more security features, including authentication and encryption.

### 2. Discover SNMP-enabled Devices
- Use tools like **Nmap** to discover devices that have SNMP enabled.
    ```bash
    nmap -sU -p 161 --script=snmp-info <target IP>
    ```

### 3. Retrieve Community Strings
- Community strings are like passwords. Common defaults are "public" for read-only access and "private" for read-write access.
- Tools like **Onesixtyone** can be used to brute force SNMP community strings.
    ```bash
    onesixtyone -c community.txt <target IP>
    ```

### 4. Query SNMP Data
- Once you have the community string, you can use tools like **snmpwalk** to query SNMP data from the device.
    ```bash
    snmpwalk -v2c -c <community string> <target IP>
    ```
- Example query:
    ```bash
    snmpwalk -v2c -c public 192.168.1.1
    ```

### 5. Analyze the Results
- The output will provide information about the device, such as the system description, uptime, interfaces, routing tables, ARP tables, etc.
- The output is often in the form of Object Identifiers (OIDs) which can be mapped to human-readable names using SNMP MIBs (Management Information Bases).

## Common Tools for SNMP Enumeration

- **Nmap**: For discovering SNMP-enabled devices.
- **Onesixtyone**: For brute-forcing SNMP community strings.
- **snmpwalk**: For retrieving information using SNMP.
- **snmpget**: To query specific OIDs.
- **snmpenum**: A script to automate the SNMP enumeration process.

## Example: Using `snmpwalk`

```bash
snmpwalk -v2c -c public 192.168.1.1
```

This command will enumerate all the SNMP OIDs available on the device with IP 192.168.1.1 using the community string public and SNMP version 2c.

**Security Considerations**

Use SNMPv3 whenever possible as it supports encryption and authentication, reducing the risk of unauthorized access.
Restrict access to SNMP interfaces to trusted IP addresses.
Change default community strings to something more secure and unique.