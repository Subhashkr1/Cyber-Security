# SMTP Enumeration Guide

Enumerating SMTP (Simple Mail Transfer Protocol) is a process used in penetration testing and security assessments to gather information about a mail server, such as valid email addresses, server software, and supported commands. This information can be valuable for further attacks or system administration.

## Steps to Enumerate SMTP

### 1. Identify SMTP Server
- Use tools like **Nmap** to discover SMTP servers on the network.
    ```bash
    nmap -p 25,587,465 --script=smtp-commands <target IP>
    ```
- The command above scans for common SMTP ports (25, 587, 465) and attempts to enumerate the supported commands.

### 2. Enumerate SMTP Commands
- Once connected to the SMTP server, you can interact with it to discover supported commands. Use **Telnet** or **Netcat** to manually interact with the SMTP service.
    ```bash
    telnet <target IP> 25
    ```
    or
    ```bash
    nc <target IP> 25
    ```
- Common commands to try:
    - `EHLO`: Extended HELO, used to identify the client to the server and list supported extensions.
    - `HELO`: Identifies the client to the server.
    - `VRFY`: Verifies if an email address exists.
    - `EXPN`: Expands a mailing list or alias to reveal individual addresses.
    - `RCPT TO`: Specifies the recipient of the email, often used in enumeration.

### 3. Enumerate Valid Email Addresses
- Use the `VRFY` command to check if specific email addresses exist on the server.
    ```bash
    VRFY user@example.com
    ```
- Use the `EXPN` command to expand mailing lists and aliases.
    ```bash
    EXPN admins
    ```
- Tools like **Metasploit** can automate this process.
    ```bash
    use auxiliary/scanner/smtp/smtp_enum
    set RHOSTS <target IP>
    set USER_FILE <usernames.txt>
    run
    ```

### 4. Analyze SMTP Banner
- SMTP servers often provide a banner when you connect, revealing information about the software version and other details.
- You can retrieve the banner by connecting to the server:
    ```bash
    nc <target IP> 25
    ```
- Example banner:
    ```
    220 mail.example.com ESMTP Postfix
    ```

### 5. Use Automated Tools
- **Nmap**: Use scripts like `smtp-commands`, `smtp-enum-users`, and `smtp-open-relay`.
    ```bash
    nmap -p 25 --script=smtp-enum-users <target IP>
    ```
- **Metasploit**: Use the SMTP enumeration modules as shown above.

## Security Considerations

- **Disable Unnecessary Commands**: Commands like `VRFY` and `EXPN` can be disabled to prevent enumeration.
- **Use SMTP Authentication**: Require authentication for sending emails to reduce the risk of misuse.
- **Monitor SMTP Logs**: Regularly monitor logs for suspicious activity related to SMTP enumeration attempts.

These steps will help you enumerate SMTP servers and gather information useful for further testing or securing your mail infrastructure.
