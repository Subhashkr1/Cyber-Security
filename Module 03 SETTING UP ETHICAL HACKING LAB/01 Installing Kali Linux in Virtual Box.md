# Installing Kali Linux on VirtualBox

This guide will walk you through the process of installing Kali Linux on VirtualBox, a popular virtualization platform.

## Prerequisites

1. **VirtualBox**: Ensure that VirtualBox is installed on your system. You can download it from [VirtualBox's official website](https://www.virtualbox.org/).
2. **Kali Linux ISO**: Download the latest Kali Linux ISO from the [Kali Linux official website](https://www.kali.org/downloads/).

## Steps to Install Kali Linux on VirtualBox

### 1. **Create a New Virtual Machine**

1. **Open VirtualBox**: Launch the VirtualBox application.

2. **Create a New VM**:
   - Click on the **"New"** button in the toolbar.
   - **Name**: Enter a name for your VM (e.g., "Kali Linux").
   - **Type**: Select "Linux."
   - **Version**: Choose "Debian (64-bit)" or "Other Linux (64-bit)" depending on your Kali Linux ISO.

3. **Configure Memory**:
   - Set the memory size for your VM. A recommended minimum is **2 GB** (2048 MB) or more, depending on your system resources.

4. **Create a Virtual Hard Disk**:
   - Select **"Create a virtual hard disk now"** and click **"Create"**.
   - Choose **VDI (VirtualBox Disk Image)** and click **"Next"**.
   - Select **"Dynamically allocated"** or **"Fixed size"** for storage type. **Dynamically allocated** grows as you use it.
   - Set the size of the virtual hard disk. A recommended minimum is **20 GB**.

### 2. **Configure VM Settings**

1. **Open VM Settings**:
   - Select the VM you created and click **"Settings"**.

2. **System Settings**:
   - Go to the **"System"** tab.
   - Uncheck **"Floppy"** from the boot order, if present.
   - Ensure **"Processor"** tab has at least **1 CPU** allocated.

3. **Storage Settings**:
   - Go to the **"Storage"** tab.
   - Click on the empty disk icon under **"Controller: IDE"**.
   - Click on the disk icon next to **"Optical Drive"** and select **"Choose a disk file"**.
   - Browse and select the Kali Linux ISO file you downloaded.

4. **Network Settings**:
   - Go to the **"Network"** tab.
   - Ensure **"Attached to"** is set to **"NAT"** or **"Bridged Adapter"** depending on your networking requirements.

### 3. **Start the Virtual Machine**

1. **Launch the VM**:
   - Select the VM and click **"Start"**.

2. **Begin Installation**:
   - The VM will boot from the Kali Linux ISO. Choose **"Graphical Install"** or **"Install"** from the boot menu.

### 4. **Follow the Installation Wizard**

1. **Language and Location**:
   - Select your preferred language, location, and keyboard layout.

2. **Configure Network**:
   - Enter a hostname (e.g., "kali").
   - Optionally set up a domain name if needed.

3. **Set Up Users and Passwords**:
   - Create a root password or user account as prompted.

4. **Partition Disks**:
   - Choose **"Guided - Use entire disk"** for simplicity or **"Manual"** for custom partitioning.
   - Confirm and write changes to disk.

5. **Install the Base System**:
   - The installer will copy files and configure the base system.

6. **Configure Package Manager**:
   - Choose whether to use a network mirror for package updates.

7. **Install GRUB Bootloader**:
   - Confirm the installation of the GRUB bootloader to the primary drive.

8. **Finish Installation**:
   - The installer will complete the setup. Once finished, the VM will prompt to restart.

### 5. **Post-Installation**

1. **Remove ISO**:
   - After restarting, go back to VirtualBox settings, **"Storage"** tab, and remove the Kali Linux ISO from the optical drive.

2. **Log In**:
   - Log in with the credentials you created during installation.

3. **Update System**:
   - Open a terminal and run the following commands to update the system:
     ```bash
     sudo apt update
     sudo apt upgrade
     ```

## Summary

You have successfully installed Kali Linux on VirtualBox. You can now start using Kali Linux for your security and penetration testing needs. Explore the features and tools available to enhance your security skills.
