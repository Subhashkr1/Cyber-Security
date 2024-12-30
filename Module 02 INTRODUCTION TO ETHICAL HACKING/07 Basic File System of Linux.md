# Basic File System of Linux

The Linux file system is organized in a hierarchical directory structure. This structure starts from a single root directory and branches out into various subdirectories. Understanding this structure is essential for navigating and managing files in Linux.

## Root Directory (`/`)

- **Description**: The top-level directory in the Linux file system hierarchy. All other directories and files are contained within it.
- **Example**: `/home`, `/etc`, `/var`

## Key Directories

### 1. **`/bin`**
   - **Description**: Contains essential binary executables (commands) required for basic system operations.
   - **Examples**: `ls`, `cp`, `mv`

### 2. **`/boot`**
   - **Description**: Contains files required for system booting, including the Linux kernel and initial RAM disk.
   - **Examples**: `vmlinuz`, `initrd.img`

### 3. **`/dev`**
   - **Description**: Contains device files representing hardware devices and virtual devices.
   - **Examples**: `/dev/sda` (hard drive), `/dev/tty` (terminal)

### 4. **`/etc`**
   - **Description**: Contains system-wide configuration files and shell scripts.
   - **Examples**: `passwd`, `fstab`, `hostname`

### 5. **`/home`**
   - **Description**: Contains personal directories for individual users.
   - **Examples**: `/home/user1`, `/home/user2`

### 6. **`/lib`**
   - **Description**: Contains essential shared libraries and kernel modules needed for system and application operation.
   - **Examples**: `libc.so`, `libm.so`

### 7. **`/media`**
   - **Description**: Used for mounting removable media such as USB drives, CDs, and DVDs.
   - **Examples**: `/media/usb`, `/media/cdrom`

### 8. **`/mnt`**
   - **Description**: Provides a temporary mount point for file systems, often used for manual mounting.
   - **Examples**: `/mnt/backup`, `/mnt/temporary`

### 9. **`/opt`**
   - **Description**: Contains optional software and third-party applications.
   - **Examples**: `/opt/spotify`, `/opt/google`

### 10. **`/proc`**
   - **Description**: Virtual file system providing information about system processes and kernel parameters.
   - **Examples**: `/proc/cpuinfo`, `/proc/meminfo`

### 11. **`/root`**
   - **Description**: The home directory for the root user (superuser).
   - **Example**: `/root`

### 12. **`/run`**
   - **Description**: Contains runtime data and information for the current boot session.
   - **Examples**: `/run/lock`, `/run/user`

### 13. **`/sbin`**
   - **Description**: Contains essential system binaries used by the superuser (root) for system maintenance.
   - **Examples**: `fsck`, `reboot`, `shutdown`

### 14. **`/srv`**
   - **Description**: Contains data for services provided by the system, such as web and FTP servers.
   - **Examples**: `/srv/www`, `/srv/ftp`

### 15. **`/tmp`**
   - **Description**: Used for temporary files created by applications and the system.
   - **Examples**: `/tmp/tempfile`, `/tmp/session`

### 16. **`/usr`**
   - **Description**: Contains user-related programs and data, including application binaries, libraries, and documentation.
   - **Examples**: `/usr/bin`, `/usr/lib`, `/usr/share`

### 17. **`/var`**
   - **Description**: Contains variable data such as logs, spool files, and temporary files that change during system operation.
   - **Examples**: `/var/log`, `/var/spool`, `/var/tmp`

## Summary

The Linux file system hierarchy is organized into a structured set of directories, each serving a specific purpose. Understanding this hierarchy helps in effective file management, system administration, and troubleshooting.
