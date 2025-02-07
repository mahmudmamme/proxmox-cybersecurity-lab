## Kali Linux VM Configuration (Overview)

This section provides an overview of the steps required to set up a Kali Linux VM. 

### 1. Prepare Proxmox

*   Download the Kali Linux ISO image.
*   Upload the ISO to your Proxmox storage.

### 2. Create the VM

*   Create a new VM in Proxmox, specifying the following:
    *   VM ID and Name
    *   Kali Linux ISO as the boot medium
    *   Sufficient disk space (e.g., 120 GB)
    *   Adequate RAM (e.g., 8 GB)
    *   Network connection to your lab network (`vmbr2` or similar).

### 3. Install Kali Linux

*   Start the VM and boot from the ISO image.
*   Follow the Kali Linux installer prompts to install the operating system.
*   Create a user account and set a strong password.

### 4. Post-Installation

*   Update the system: `sudo apt update && sudo apt upgrade -y`
*   Install any additional tools required for your security tasks.

### 5. Network Verification

*   Verify that the VM receives an IP address from the pfSense DHCP server in your lab network.
*   Test network connectivity by pinging the pfSense LAN IP address.

### 6. Optional Enhancements

*   Configure SSH access for remote management.
*   Install the QEMU Guest Agent for improved performance.

### 7. Network Segmentation (if using VLANs)

*   Configure VLANs in pfSense (if desired) to segment your network.
*   Create firewall rules to control traffic flow between VLANs.
*   Configure DHCP servers for each VLAN.

**Important Notes:**

*   Ensure that your pfSense firewall is properly configured to protect your lab environment.
*   Keep your Kali Linux VM updated with the latest security patches.
