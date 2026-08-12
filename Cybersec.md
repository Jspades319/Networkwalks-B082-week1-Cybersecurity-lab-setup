# Cybersecurity Lab Environment Setup  
_Isolated virtual lab for penetration testing and ethical hacking practice_

---

## Overview  
This guide explains how to install VirtualBox, create a Kali Linux virtual machine (VM), and configure NAT networking for internet access. This lab environment is ideal for safe cybersecurity testing on systems you own or have permission to test.

---

## Prerequisites  
- Host OS with hardware virtualization enabled (VT-x/AMD-V)  
- VirtualBox (latest stable version)  
- Kali Linux ISO (64-bit installer recommended)  

---

## Step 1: Download and Install VirtualBox  
1. Go to the [VirtualBox official website](https://www.virtualbox.org/)  
2. Download the installer for your OS (Windows/macOS/Linux)  
3. Run the installer and follow the wizard:  
   - Accept license agreement  
   - Use default installation options  
   - Allow network interfaces installation if prompted  
4. Complete installation and launch VirtualBox  

---

## Step 2: Download Kali Linux ISO  
1. Visit the [Kali Linux download page](https://www.kali.org/get-kali/)  
2. Download the appropriate ISO image (64-bit installer recommended)  

---

## Step 3: Create a New Virtual Machine in VirtualBox  
1. Open VirtualBox and click **New**  
2. Enter VM details:  
   - Name: `Kali Linux`  
   - Type: `Linux`  
   - Version: `Debian (64-bit)`  
3. Allocate memory (RAM):  
   - Minimum 2048 MB (2 GB)  
   - Recommended 4096 MB (4 GB) if available  
4. Create a virtual hard disk:  
   - Select **Create a virtual hard disk now**  
   - Choose **VDI (VirtualBox Disk Image)**  
   - Select **Dynamically allocated**  
   - Set size to at least 20 GB  
5. Click **Create**  

---

## Step 4: Configure Network to NAT  
1. Select the Kali VM and click **Settings**  
2. Go to the **Network** tab  
3. Ensure **Adapter 1** is enabled  
4. Set **Attached to:** to **NAT**  
   - This allows the VM to access the internet through the host machine  

---

## Step 5: Mount Kali Linux ISO and Start VM  
1. In VM **Settings**, go to **Storage**  
2. Under **Controller: IDE** or **SATA**, select the empty optical drive  
3. Click the disk icon and choose **Choose a disk file**  
4. Select the downloaded Kali Linux ISO  
5. Click **Start** to boot the VM from the ISO  

---

## Step 6: Install Kali Linux  
1. At the Kali boot menu, select **Graphical install** or **Install**  
2. Follow the on-screen prompts:  
   - Select language, location, keyboard layout  
   - Configure network (hostname optional)  
   - Create user account and password  
   - Partition disks (guided partitioning recommended)  
   - Confirm and write changes to disk  
   - Install base system and additional software  
   - Install GRUB bootloader to the master boot record  
3. Finish installation and reboot  

---

## Step 7: Finalize Setup  
1. After reboot, go to VM **Settings** → **Storage**  
2. Remove the Kali Linux ISO from the virtual optical drive  
3. Start the VM normally; Kali Linux should boot from the virtual hard disk  

---

## Step 8: Verify Network Connectivity  
If using Kali Linux 2026.1 or higher, run the following command in a terminal to fix potential network issues:  
```bash
sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
