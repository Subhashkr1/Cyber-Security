# Default Ports

In computer networking, certain services and protocols use well-known ports by default. These ports are standardized to ensure that networked applications and services can communicate effectively. Below is a list of common default ports and their associated services.

## Common Default Ports

| Port Number | Protocol | Service              | Description                                                |
|-------------|----------|----------------------|------------------------------------------------------------|
| 20          | TCP      | FTP Data             | File Transfer Protocol (data transfer)                     |
| 21          | TCP      | FTP Control          | File Transfer Protocol (control commands)                  |
| 22          | TCP      | SSH                  | Secure Shell (encrypted remote login and command execution)|
| 23          | TCP      | Telnet               | Telnet (unencrypted remote login)                          |
| 25          | TCP      | SMTP                 | Simple Mail Transfer Protocol (email transmission)         |
| 53          | UDP      | DNS                  | Domain Name System (domain name resolution)                |
| 67          | UDP      | DHCP Server          | Dynamic Host Configuration Protocol (server-side)          |
| 68          | UDP      | DHCP Client          | Dynamic Host Configuration Protocol (client-side)          |
| 80          | TCP      | HTTP                 | Hypertext Transfer Protocol (web traffic)                  |
| 110         | TCP      | POP3                 | Post Office Protocol v3 (email retrieval)                  |
| 143         | TCP      | IMAP                 | Internet Message Access Protocol (email retrieval)         |
| 443         | TCP      | HTTPS                | HTTP Secure (encrypted web traffic)                        |
| 3389        | TCP      | RDP                  | Remote Desktop Protocol (remote desktop services)          |
| 5432        | TCP      | PostgreSQL           | PostgreSQL Database (default port for PostgreSQL)          |
| 6379        | TCP      | Redis                | Redis Database (default port for Redis)                    |
| 27017       | TCP      | MongoDB              | MongoDB Database (default port for MongoDB)                |

## Usage and Security Considerations

- **Default Ports:** These ports are commonly used by default, but they can often be reconfigured. Changing default ports can sometimes enhance security by obscuring the service.
- **Security:** Open ports can be potential security risks. It’s essential to secure services and applications running on these ports and monitor them for unauthorized access.
- **Port Scanning:** Tools like Nmap can be used to discover open ports and identify services running on a network.

## Conclusion

Understanding default ports is crucial for configuring and securing network services. While these ports are standardized, it's important to be aware of potential security implications and adjust configurations as needed to safeguard your systems.
