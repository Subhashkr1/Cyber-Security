Sniffing with Wireshark
Wireshark is one of the most popular network protocol analyzers used for packet capturing and network traffic analysis. It allows you to intercept and examine packets transmitted over a network in real-time, making it a powerful tool for network administrators, security professionals, and ethical hackers. It can be used to perform sniffing attacks, inspect network traffic, troubleshoot network issues, or analyze malware.

Steps to Perform Sniffing with Wireshark
Step 1: Install Wireshark
Windows:

Download Wireshark from Wireshark official website.
Run the installer and follow the on-screen instructions.
Linux (Debian/Ubuntu):

Open the terminal and run:
bash
Copy code
sudo apt-get install wireshark
MacOS:

Install via Homebrew:
bash
Copy code
brew install wireshark
Step 2: Launch Wireshark
After installing Wireshark, launch the application.

You'll be prompted to select an interface. The interface corresponds to the network device on which you want to capture traffic. This could be a Wi-Fi adapter, Ethernet port, or a virtual network interface.

On Windows: You might see interfaces like "Wi-Fi" or "Ethernet."
On Linux/MacOS: You may see interfaces like eth0, wlan0, lo (loopback), etc.
Select the correct interface and click on Start to begin capturing packets.

Step 3: Capture Packets
Once you start capturing, Wireshark will display a live list of network packets passing through the selected interface. Each packet contains details like source, destination, protocol, and more.

By default, Wireshark will capture all packets from the selected network interface. You can apply filters to focus on specific types of traffic.

Step 4: Apply Display Filters
Wireshark provides powerful filters to focus on specific types of traffic. Here are a few common examples:

HTTP Traffic:

bash
Copy code
http
This filter captures all HTTP traffic, including web requests and responses.

TCP Traffic:

bash
Copy code
tcp
This filter captures all TCP traffic, including HTTP, FTP, and other TCP-based protocols.

DNS Traffic:

bash
Copy code
dns
This filter shows only DNS queries and responses.

ICMP (Ping):

bash
Copy code
icmp
This captures ICMP packets, including ping requests and replies.

IP Address Specific:

bash
Copy code
ip.addr == 192.168.1.10
This filter captures packets from or to a specific IP address.

Port Filtering:

bash
Copy code
tcp.port == 80
Captures packets on a specific port, in this case, port 80 for HTTP traffic.

Step 5: Analyzing Captured Packets
Each captured packet can be examined in detail. To view the packet data, click on any packet in the capture window. You’ll see a breakdown of the packet in different layers:

Frame: Contains the metadata of the packet (time, size, etc.).
Ethernet: Shows Ethernet header details (e.g., MAC addresses).
IP: Displays IP address information (source and destination).
TCP/UDP: Protocol details such as source and destination port numbers.
Application Layer: This could include HTTP headers, DNS queries, etc., depending on the protocol.
You can expand each section to view more detailed information. For example, for an HTTP packet, you might see the HTTP method, host, and other headers.

Step 6: Save and Export Captures
If you wish to save the captured packets for later analysis or sharing, do the following:

Go to File > Save As or File > Export.
Choose a file format for saving, such as PCAP (Packet Capture) or TXT for plain text.
Wireshark can also export specific packets that match a filter to a new file, making it easy to analyze only the relevant traffic.

Step 7: Stop Capturing
Once you have captured the desired traffic, you can stop the capture by clicking the Stop button in Wireshark.

Performing Sniffing in Specific Scenarios
Sniffing on a Local Network
Promiscuous Mode: Wireshark can be configured to put the network interface into promiscuous mode, which allows it to capture all traffic, even if the traffic is not addressed to the machine running Wireshark.

ARP Spoofing: In some cases, an attacker might use ARP poisoning (using tools like Ettercap or Cain & Abel) to redirect traffic to their machine. After performing ARP poisoning, you can use Wireshark to sniff the traffic that passes through your machine.

In Wireshark, you’ll be able to see the packets that were originally intended for other machines.
Monitoring DNS Traffic: By using the dns filter, you can capture DNS queries and responses, which might reveal which websites users are trying to access or malicious redirections.

Sniffing HTTPS Traffic
If you're trying to capture HTTPS traffic, it will be encrypted, and you won't see the actual contents of the data (e.g., the HTTP headers or web page contents). However, you can still capture the TLS handshake and related metadata, such as:

The server's SSL/TLS certificate.
The ciphers used for encryption.
The server name in the SNI field.
To decrypt HTTPS traffic, you need access to the server's private key or use a method like SSL/TLS interception (commonly done with a MITM proxy like mitmproxy).

Capturing Packets on a Wi-Fi Network
Wireshark can capture Wi-Fi traffic if you have a Wi-Fi adapter that supports monitor mode. This allows you to sniff packets over wireless networks (even if you're not directly connected to the network).

Wireshark Filtering Examples
Capture only HTTP traffic:

bash
Copy code
tcp.port == 80
This filter captures packets on port 80 (standard for HTTP).

Capture packets between two IPs:

bash
Copy code
ip.addr == 192.168.1.10 && ip.addr == 192.168.1.20
Filter by specific protocol:

ICMP (Ping packets):

bash
Copy code
icmp
DNS:

bash
Copy code
dns
Display HTTP traffic with specific User-Agent:

bash
Copy code
http.user_agent contains "Mozilla"
Important Considerations and Ethics
Legality: Sniffing network traffic without permission is illegal in many jurisdictions and can lead to serious consequences. Always have explicit consent from the network owner before performing any sniffing activities.

Data Privacy: Be mindful that sniffing can capture sensitive data, such as passwords, personal information, and credit card details. Always respect privacy and confidentiality when using sniffing tools like Wireshark.

Use in Ethical Hacking: Wireshark is widely used for network analysis, penetration testing, and troubleshooting. In an ethical hacking context, it helps identify weaknesses in the network, such as cleartext protocols that transmit sensitive data insecurely.