# Proxmox Base Setup: Hardware and Software Requirements

This guide outlines the hardware and software required to establish a foundation for a cybersecurity home lab using Proxmox Virtual Environment (VE).

## 1. Hardware Requirements

The following hardware setup is recommended to provide sufficient resources for running multiple virtual machines (VMs) and services concurrently:

*   **Host Machine:** Dell Optiplex 7050 Mini PC (Example)

    *   **CPU:** Intel Core i5-7500T (Quad-Core, 2.70 GHz) - *Minimum Requirement*
    *   **RAM:** 32GB DDR4 (expandable as needed) - *Recommended, 16GB minimum*
    *   **Storage:** 1TB SSD (Proxmox installed with additional storage for VMs) - *SSD highly recommended for performance*
    *   **Network:** Built-in Ethernet port + USB Wi-Fi Adapter (for network segmentation and internet access, if desired)
    *   **Power Supply:** 130W external power adapter (or suitable for the chosen hardware)

    *Note:* This setup allows for a robust environment, providing ample CPU and memory resources for hosting VMs without significant performance degradation.

*   **Optional Hardware Upgrades:**

    *   Higher-end processor (for increased VM density and performance).
    *   Additional RAM (for resource-intensive VMs or large-scale security monitoring).
    *   Additional SSD or NVMe storage (for increased VM storage capacity and I/O performance).

## 2. Software Requirements

The following software components are required to run this home lab:

### 2.1 Host Software

*   **Proxmox Virtual Environment (VE):**

    *   A free and open-source virtualization platform based on Debian Linux, used to manage and host all virtual machines.
    *   **Download Link:** [Proxmox VE](https://www.proxmox.com/en/proxmox-ve)
    *   *Note:* Follow the official Proxmox VE installation guide to install Proxmox on the host machine.

### 2.2 Virtual Machines and Services: ISOs and Links

The following virtual machines and services will be installed on Proxmox VE. Download the necessary ISOs or installation packages:

1.  **pfSense:**

    *   A free and open-source firewall/router to manage network traffic and segmentation within the lab.
    *   **Download Link:** [pfSense](https://www.pfsense.org/download/)

2.  **Kali Linux:**

    *   A Debian-based distribution used for penetration testing, ethical hacking, and security auditing.
    *   **Download Link:** [Kali Linux](https://www.kali.org/get-kali/)

3.  **Wazuh:**

    *   A free, open-source security platform that provides real-time threat detection, response, and compliance monitoring.
    *   **Download Link:** [Wazuh](https://wazuh.com/)
        *Note: This download leads to a landing page rather than the direct iso, further configuration will be needed.*

4.  **Security Onion:**

    *   A free and open-source platform for network security monitoring, intrusion detection, and log management.
    *   **Download Link:** [Security Onion](https://securityonion.net/)

5.  **TheHive & Cortex:**

    *   Open-source incident response platforms that help track, analyze, and respond to cyber threats. *Note: A ubuntu server will be required to run the server.*
    *   **Download Link:** [TheHive](https://thehive-project.org/) & [Cortex](https://thehive-project.org/)
        *Note: These downloads lead to a project page rather than the direct iso, further configuration will be needed.*

6.  **Metasploitable 2 & DVWA (Damn Vulnerable Web Application):**

    *   Vulnerable machines used for practicing penetration testing and exploitation techniques.
    *   **Download Link (Metasploitable 2):** [Metasploitable 2](https://sourceforge.net/projects/metasploitable/files/Metasploitable2/)
    *   **Download Link (DVWA):** [DVWA GitHub](https://github.com/digininja/DVWA) *Note: This download leads to a github page rather than the direct file download. further configuration will be needed.*

7.  **Windows Server 2022:**

    *   A VM running Active Directory to simulate a real-world domain environment with user accounts, policies, and domain controllers. *Note: A license is required, without the license the system will only be functional for 180 days.*
    *   **Download Link:** [Windows Server Evaluation](https://www.microsoft.com/en-us/evalcenter/evaluate-windows-server)

8.  **Ubuntu with Docker & Portainer:**

    *   **Ubuntu:** A Linux-based distribution used for running services such as Docker.
    *   **Docker:** An open-source platform to automate application deployment in containers.
    *   **Portainer:** A simple management UI for Docker, running in a lightweight container.
    *   **Download Links:**
        *   [Ubuntu](https://ubuntu.com/download/server)
        *   [Docker](https://docs.docker.com/get-docker/)
        *   [Portainer](https://www.portainer.io/installation)
            *Note: The linked Portainer page contains instructions, rather than a direct link to the file.*

## 3. Proxmox VE Installation

1.  **Download the Proxmox VE ISO:** Use the link in section *2.1 Host Software*.
2.  **Create Bootable Media:** Use a tool like Rufus ([https://rufus.ie/en/](https://rufus.ie/en/)) to create a bootable USB drive from the Proxmox VE ISO.
3.  **Boot from USB:** Insert the USB drive into the host machine and boot from it.
    *   The BIOS/UEFI settings may need to be adjusted to prioritize booting from USB.
4.  **Follow the On-Screen Prompts:** The Proxmox VE installer will guide the install process, including disk partitioning and network configuration.

*Note:* During the installation, a static IP address is recommended.

## 4. Post-Installation Tasks

1.  **Access the Proxmox Web Interface:** After the installation completes, access the Proxmox web interface through a web browser using the IP address assigned during installation (e.g., `https://your_proxmox_ip:8006`).
2.  **Upload ISO Images:** Upload the ISO images downloaded in *Section 2.2 Virtual Machines and Services* to a Proxmox storage repository (e.g., `local`).
3.  **Configure Storage:** Configure additional storage if desired, such as adding an external hard drive or network storage.

---

These hardware and software components form the foundation of the home lab, enabling the creation of a secure, isolated environment for learning, testing, and experimentation. Ensure the hardware is capable of supporting the virtual machines listed above to avoid performance issues. Follow the linked guides for each software for set up.

---
*Note*
Please keep in mind each ISO may differ on version. The installation might be different than described.
