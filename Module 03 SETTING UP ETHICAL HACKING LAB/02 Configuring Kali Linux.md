# Configuring Kali Linux on VirtualBox

## Prerequisites

1. **Download and Install VirtualBox**: 
   - Go to [VirtualBox Downloads](https://www.virtualbox.org/wiki/Downloads) and download the latest version of VirtualBox for your operating system.
   - Follow the installation instructions for your OS.

2. **Download Kali Linux ISO**:
   - Visit the [Kali Linux Downloads](https://www.kali.org/downloads/) page.
   - Download the appropriate ISO image for Kali Linux.

## Creating a New Virtual Machine

1. **Open VirtualBox**:
   - Launch VirtualBox from your applications menu.

2. **Create a New Virtual Machine**:
   - Click on `New` to start the creation wizard.
   - Name: Enter a name for your VM (e.g., "Kali Linux").
   - Type: Select `Linux`.
   - Version: Choose `Debian (64-bit)`.

3. **Configure Memory**:
   - Allocate memory (RAM) to your VM. A recommended minimum is 2 GB.

4. **Create a Virtual Hard Disk**:
   - Choose `Create a virtual hard disk now` and click `Create`.
   - Select `VDI (VirtualBox Disk Image)` and click `Next`.
   - Choose `Dynamically allocated` and click `Next`.
   - Set the size of the virtual hard disk. A recommended minimum is 20 GB. Click `Create`.

## Configuring the Virtual Machine

1. **Select Your Virtual Machine**:
   - Click on your new VM in the list and then click on `Settings`.

2. **System Settings**:
   - Go to the `System` tab.
   - Under the `Motherboard` tab, ensure that `Floppy` is unchecked, and `Optical` is checked.
   - Adjust the `Processor` tab if you want to allocate more CPU cores.

3. **Storage Settings**:
   - Go to the `Storage` tab.
   - Under `Controller: IDE`, click on `Empty`.
   - Click on the disk icon next to `Optical Drive` and select `Choose a disk file`.
   - Browse and select the Kali Linux ISO file you downloaded.

4. **Network Settings**:
   - Go to the `Network` tab.
   - Ensure `Adapter 1` is attached to `NAT` for internet access.

## Installing Kali Linux

1. **Start the Virtual Machine**:
   - Click on `Start` to boot the VM from the Kali Linux ISO.

2. **Begin Installation**:
   - Select `Graphical Install` from the Kali Linux boot menu.

3. **Follow Installation Steps**:
   - Choose your preferred language, location, and keyboard layout.
   - Configure network settings (you can use the default settings).
   - Set up a root password (remember this for future logins).
   - Partition the disks (select `Guided - Use entire disk` for simplicity).
   - Follow the prompts to complete the installation.

4. **Complete the Installation**:
   - Once the installation is complete, the VM will prompt you to remove the installation media and reboot.
   - Go back to `Settings` in VirtualBox and remove the Kali Linux ISO from the storage settings.
   - Reboot the VM.

## Post-Installation Configuration

1. **Install VirtualBox Guest Additions**:
   - Start Kali Linux.
   - Open a terminal and install the necessary packages:

     ```bash
     sudo apt update
     sudo apt install -y build-essential dkms linux-headers-$(uname -r)
     ```

   - In VirtualBox, go to `Devices` > `Insert Guest Additions CD image`.
   - Follow the on-screen instructions to install Guest Additions.

2. **Update Kali Linux**:
   - Open a terminal and run:

     ```bash
     sudo apt update
     sudo apt upgrade
     ```

3. **Configure Shared Folders** (optional):
   - Go to `Settings` > `Shared Folders`.
   - Click `Add` to create a shared folder between the host and the VM.

## Conclusion

Your Kali Linux VM should now be fully configured and ready for use. You can start using it for your cybersecurity and penetration testing needs.
