## pfSense Firewall Configuration

This section outlines the process of setting up pfSense as the central firewall for the home lab, enabling network segmentation and security.

### 1. Proxmox Preparation

*   **Download pfSense ISO:** Download the pfSense ISO image from the official pfSense website.
*   **Upload to Proxmox:** Upload the ISO to the Proxmox storage.
*   **Create Linux Bridge (Optional):** An additional Linux bridge can be created in Proxmox (e.g., `vmbr2`) if a separate LAN network is required for the lab. Ensure VLAN awareness is enabled for the bridge.

### 2. Create the pfSense Virtual Machine

*   **Create VM:** In Proxmox, create a new virtual machine and select the uploaded pfSense ISO as the boot medium.
*   **Configure Network:** Add network interfaces to the VM: one for WAN (connected to the internet or main network), and one or more for LAN (connected to the internal lab network(s)).
*   **Install pfSense:** Start the VM and follow the pfSense installer.

### 3. Basic pfSense Configuration

*   **Interface Assignment:** During the initial setup, assign the network interfaces to the WAN and LAN roles.
*   **LAN IP Address:** Configure a static IP address for the LAN interface (e.g., `10.10.1.254/24`).
*   **Web Interface Access:** The pfSense web interface can be accessed using the LAN IP address.
*   **Setup Wizard:** Run through the pfSense setup wizard to configure basic settings (hostname, DNS, etc.).

### 4. Network Segmentation with VLANs (Optional)

*   **Define VLANs:** In the pfSense web interface, create VLANs for different network segments (e.g., VLAN 10 for a vulnerable network, VLAN 20 for a secure network).
*   **Assign VLANs to Interfaces:** Assign each VLAN to a virtual interface on the pfSense LAN.
*   **Configure VLAN Interface Settings:** Configure a static IP address for each VLAN interface.

### 5. Firewall Rules

*   **Create Firewall Rules:** Create firewall rules to control traffic flow between the different network segments.
*   **Default Deny:** Implement a default-deny policy, allowing only necessary traffic.
*   **Specific Rules:** Create rules to allow specific traffic between VLANs, or to the internet (if needed).

### 6. DHCP Server

*   **Enable DHCP:** Enable the DHCP server on each LAN and VLAN interface to automatically assign IP addresses to VMs.
*   **Configure DHCP Ranges:** Define IP address ranges for each DHCP server.
*   **DNS Configuration:** Specify the DNS server(s) to be used by the DHCP clients.

**Important Considerations:**

*   **Security:** Carefully plan the firewall rules to ensure that the lab environment is properly isolated and protected.
*   **Documentation:** Refer to the official pfSense documentation for detailed configuration options.
*   **VLAN Awareness:** When setting up the Linux Bridge in proxmox, ensure the *VLAN Aware* box is checked.
*   **Default password**: Make sure to change the default `admin` password.

**Detailed Configuration:**

A detailed step-by-step guide with screenshots can be found in [configurations/pfsense_setup.md](configurations/pfsense_setup.md).

---
