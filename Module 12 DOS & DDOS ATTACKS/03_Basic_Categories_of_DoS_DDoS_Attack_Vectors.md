# Basic Categories of DoS/DDoS Attack Vectors

DoS and DDoS attacks can be broadly categorized based on the method used to disrupt the target's services. Each attack vector targets specific aspects of the system, network, or application to overwhelm and disable it. 

---

## 1. **Volumetric Attacks**
These attacks aim to consume all the available bandwidth between the target system and the rest of the internet by flooding it with massive amounts of traffic.

### Key Features:
- High volume of requests or data packets.
- Exploits the target's limited bandwidth capacity.
- Traffic originates from multiple sources (in DDoS attacks).

### Examples:
- **UDP Flood**: Sends a high volume of UDP packets to random ports.
- **DNS Amplification**: Exploits open DNS resolvers to amplify traffic sent to the victim.
- **NTP Amplification**: Leverages vulnerable Network Time Protocol servers for traffic amplification.

---

## 2. **Protocol Attacks**
Also known as state-exhaustion attacks, these focus on depleting the resources of servers, firewalls, or load balancers by exploiting weaknesses in network protocols.

### Key Features:
- Targets session-handling mechanisms.
- Overwhelms the connection state tables of devices.

### Examples:
- **SYN Flood**: Sends a large number of SYN requests without completing the TCP handshake.
- **Ping of Death**: Sends oversized or malformed ICMP packets to crash the system.
- **Smurf Attack**: Sends ICMP requests with a spoofed source IP, causing devices to send replies to the victim.

---

## 3. **Application Layer Attacks**
These attacks target vulnerabilities at the application level, aiming to exhaust the server's processing power or memory.

### Key Features:
- Mimics legitimate traffic, making it harder to detect.
- Consumes server resources without requiring a high volume of traffic.

### Examples:
- **HTTP Flood**: Overwhelms the web server by sending numerous HTTP requests.
- **Slowloris**: Opens multiple HTTP connections and keeps them active to exhaust server resources.
- **DNS Query Flood**: Sends a high number of DNS requests to overload the DNS server.

---

## Comparison of DoS/DDoS Attack Categories

| **Category**        | **Target**                  | **Purpose**                                   | **Examples**                       |
|----------------------|----------------------------|-----------------------------------------------|-------------------------------------|
| **Volumetric**      | Bandwidth                  | Consume all available network bandwidth       | UDP Flood, DNS Amplification        |
| **Protocol**        | Network Protocols          | Deplete resources like connection state tables | SYN Flood, Ping of Death            |
| **Application Layer** | Applications and Services | Exhaust server processing power or memory     | HTTP Flood, Slowloris               |

---

## Hybrid Attacks
Many attackers combine multiple categories to create **multi-vector attacks**, which are harder to mitigate. For example:
- A combination of a volumetric attack (e.g., UDP flood) with an application-layer attack (e.g., HTTP flood).

---

## Mitigation Strategies
1. **Volumetric Attacks**:
   - Use Content Delivery Networks (CDNs) and load balancers.
   - Implement traffic filtering with firewalls.
2. **Protocol Attacks**:
   - Configure firewalls and routers to drop malformed packets.
   - Use SYN cookies to manage incomplete TCP connections.
3. **Application Layer Attacks**:
   - Monitor server logs for unusual activity.
   - Implement rate-limiting for application requests.

Understanding these categories helps in devising comprehensive defense strategies to protect against DoS and DDoS attacks.
