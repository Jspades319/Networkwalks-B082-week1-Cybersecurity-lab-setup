# Kali Linux VM Setup Tutorial with VirtualBox and NAT

This repository provides a step-by-step guide to install VirtualBox, create a Kali Linux virtual machine (VM) with NAT networking, and configure it for lab use. It is designed for beginners who want to set up a Kali Linux environment for cybersecurity practice.

---

## Video Tutorial

You can watch the full video tutorial here:  
[https://youtu.be/c4E7QivN5Dw](https://youtu.be/c4E7QivN5Dw)

---

## Project Overview and Objectives

- Download and install VirtualBox on your host machine.
- Download the Kali Linux ISO image.
- Create and configure a Kali Linux VM with appropriate settings.
- Set up NAT networking to allow internet access from the VM.
- Install Kali Linux on the VM.
- Verify network connectivity.
- Create snapshots to save VM states for easy rollback.

---

## Configuration Table

| Item                  | Value                          |
|-----------------------|--------------------------------|
| VM Name               | Kali Linux                     |
| Operating System Type | Linux                          |
| OS Version            | Debian (64-bit) (Kali Linux)  |
| RAM                   | 2048 MB (2 GB) minimum, 4096 MB recommended |
| Virtual Hard Disk Type | VDI (VirtualBox Disk Image)   |
| Disk Size             | At least 20 GB                |
| Network Adapter       | NAT                           |

---

## Step-by-Step Setup Guide

### 1. Download and Install VirtualBox

- Go to the official VirtualBox website: [https://www.virtualbox.org/](https://www.virtualbox.org/)
- Download the installer for your operating system.
- Run the installer and follow the wizard steps.
- Accept license agreements and allow network interfaces installation if prompted.
- Complete installation and launch VirtualBox.

### 2. Download Kali Linux ISO

- Visit the official Kali Linux website: [https://www.kali.org/get-kali/](https://www.kali.org/get-kali/)
- Download the 64-bit installer ISO image.

### 3. Create a New Virtual Machine

- Open VirtualBox and click **New**.
- Name the VM (e.g., "Kali Linux").
- Set Type to **Linux** and Version to **Debian (64-bit)**.
- Allocate RAM (2048 MB minimum, 4096 MB recommended).
- Create a virtual hard disk:
  - Choose **Create a virtual hard disk now**.
  - Select **VDI** as the disk type.
  - Choose **Dynamically allocated** storage.
  - Set disk size to at least 20 GB.
- Click **Create**.

### 4. Configure Network to NAT

- Select your Kali VM and click **Settings**.
- Go to the **Network** tab.
- Ensure **Adapter 1** is enabled and attached to **NAT**.

### 5. Mount Kali Linux ISO and Start VM

- In **Settings > Storage**, select the empty optical drive.
- Click the disk icon and choose the Kali Linux ISO file.
- Start the VM to boot from the ISO.

### 6. Install Kali Linux

- Select **Graphical install** or **Install** from the boot menu.
- Follow the prompts to:
  - Select language, location, and keyboard.
  - Configure network and hostname.
  - Set up user account and password.
  - Partition disks (guided partitioning recommended).
  - Install base system and additional software.
  - Install GRUB bootloader.
- Finish installation and reboot.

### 7. Final Steps

- Remove the Kali Linux ISO from the virtual drive to avoid booting from it again.
- Start the VM normally.
- Verify network connectivity by running:
  ```bash
  sudo nmcli connection modify "Wired connection 1" ipv4.dad-timeout 0
