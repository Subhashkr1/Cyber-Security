# NFS Enumeration Guide

Network File System (NFS) enumeration is the process of gathering information about shared directories and files on a network that uses the NFS protocol. This can be useful for system administrators as well as penetration testers looking to identify potential vulnerabilities.

## Steps to Enumerate NFS

### 1. Discover NFS Shares
- Use **Nmap** to discover NFS services running on a target network.
    ```bash
    nmap -p 111 --script=nfs-ls,nfs-statfs,nfs-showmount <target IP>
    ```
- The `-p 111` specifies the port for the RPCbind service, which NFS relies on.

### 2. Enumerate NFS Shares Using `showmount`
- The `showmount` command displays the shared directories from the NFS server.
    ```bash
    showmount -e <target IP>
    ```
- This command lists all the NFS exports (shared directories) and the clients that can mount them.

### 3. Check Access Permissions
- After identifying shared directories, you can manually mount them to check access permissions.
    ```bash
    sudo mount -t nfs <target IP>:/<shared directory> /mnt/nfs
    ```
- Example:
    ```bash
    sudo mount -t nfs 192.168.1.100:/shared_folder /mnt/nfs
    ```
- Check if you have read, write, or execute permissions on the mounted directory.

### 4. Enumerate Files and Directories
- Once mounted, you can list files and directories to see what is available.
    ```bash
    ls -la /mnt/nfs
    ```

### 5. Use Nmap for Detailed Enumeration
- **Nmap** scripts can be used for further NFS enumeration.
    - **nfs-ls**: Lists files and directories.
        ```bash
        nmap --script=nfs-ls -p 111 <target IP>
        ```
    - **nfs-showmount**: Lists shared directories.
        ```bash
        nmap --script=nfs-showmount -p 111 <target IP>
        ```
    - **nfs-statfs**: Retrieves information about the filesystem.
        ```bash
        nmap --script=nfs-statfs -p 111 <target IP>
        ```

### 6. Automate Enumeration with Metasploit
- Metasploit has modules for NFS enumeration.
    ```bash
    use auxiliary/scanner/nfs/nfsmount
    set RHOSTS <target IP>
    run
    ```

## Security Considerations

- **Restrict NFS Access**: Limit access to NFS shares to trusted IP addresses only.
- **Use Proper Permissions**: Ensure that NFS shares have appropriate permissions to prevent unauthorized access.
- **Disable Unnecessary NFS Services**: If NFS is not required, disable it to reduce the attack surface.
- **Regularly Monitor**: Keep an eye on NFS logs and traffic to detect any unauthorized access or enumeration attempts.

These steps will help you enumerate NFS shares and gather critical information about file sharing on a network.
