# Kali Linux VM Configuration (Overview)

This guide provides an overview of the steps required to set up a Kali Linux VM in the Proxmox environment. 

### 1. Proxmox Preparation

*   Download the Kali Linux ISO.
*   Upload the ISO to Proxmox storage.

### 2. VM Creation

*   Create a new VM in Proxmox, specifying:
    *   VM ID and Name (e.g., `prod-kali`, VM ID `202`)
    *   Kali Linux ISO as the boot medium
    *   Sufficient disk space (e.g., 120 GB)
    *   Adequate RAM (e.g., 8 GB)
    *   Network connection to the lab network (e.g., `vmbr2`).

### 3. Kali Linux Installation

*   Start the VM and boot from the ISO.
*   Follow the Kali Linux installer prompts.
*   Set up a user account and password.

### 4. Post-Installation

*   Update the system: `sudo apt update && sudo apt upgrade -y`

### 5. Network Verification

*   Verify the VM receives an IP address from the DHCP server.
*   Test network connectivity by pinging the pfSense LAN IP address.

### 6. Optional Configuration

*   Configure SSH access (if desired): `sudo apt install openssh-server -y`
*   Install QEMU Guest Agent for improved performance: `sudo apt install qemu-guest-agent -y`

### 7. VLAN Configuration (if applicable)

*   Configure VLANs, firewall rules, and DHCP server settings in pfSense, as needed.

**Key Considerations:**

*   Ensure the Proxmox firewall allows necessary traffic to and from the Kali Linux VM.
*   Keep the Kali Linux VM updated with the latest security patches.
