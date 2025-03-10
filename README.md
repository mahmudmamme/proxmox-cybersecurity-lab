# Proxmox Cybersecurity Home Lab

[![License](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)  (Optional: Add a license badge)

## Overview

Welcome to my home lab project! This environment is designed to provide a comprehensive sandbox for learning, testing, and experimenting with various cybersecurity tools and techniques. The core of the lab is hosted on **Proxmox VE**, a powerful open-source virtualization platform, which allows me to run multiple virtual machines (VMs) for different security purposes.

### Objectives

*   Learn and experiment with **network security** tools.
*   Simulate and monitor **real-world cyber threats**.
*   Host and configure **vulnerable machines** for penetration testing.
*   Practice **incident detection** and **response** in a controlled environment.

## Lab Components

This home lab includes several tools and technologies, each playing a key role in the overall security setup:

*   **Proxmox VE:**  Virtualization platform hosting all VMs.
*   **pfSense:** Open-source firewall and router for network segmentation and security.
*   **Kali Linux:** Penetration testing operating system for offensive security assessments and vulnerability analysis.
*   **Wazuh:** Host-based intrusion detection system (HIDS) for real-time monitoring, log analysis, and security event management.
*   **Ubuntu with Docker & Portainer:** Containerized environments for managing applications and services, simplifying deployment and scaling.
*   **Active Directory (Windows Server 2022, Windows 10 & 11):** Domain services for testing security policies, access control, and simulating enterprise network environments.
*   **Nessus:** A widely-used vulnerability scanner for identifying security weaknesses, misconfigurations, and missing patches across systems and applications. Nessus helps to prioritize remediation efforts by providing detailed reports and risk scores.
*   **Metasploitable 2 & DVWA (Damn Vulnerable Web Application):**  Intentionally vulnerable machines and web applications for ethical hacking practice and security testing.
*   **Security Onion:** A free and open-source Linux distribution for threat hunting, enterprise security monitoring, and log management.
*   **TheHive & Cortex:** Incident response platform for managing, investigating, and analyzing cyber threats, facilitating collaboration and automation.

## Network Diagram

Below is the high-level network topology for the home lab, showing how all components are interconnected and segmented into various subnets. 

![Network Diagram](https://github.com/mamme206/proxmox-cybersecurity-lab/blob/main/Image/Network%20Diagram.png)


## Key Features

*   **Multi-Layer Security:** Segmented network with firewalls, IDS/IPS, and comprehensive logging to monitor for threats at various levels.
*   **Vulnerability Testing:** A safe and controlled environment for practicing penetration testing techniques using tools like **Kali Linux** and exploiting vulnerabilities in **Metasploitable 2** and **DVWA**.
*   **Threat Monitoring & Response:** Real-time alerts and proactive incident management using tools like **Wazuh**, **Security Onion**, and **TheHive**, enabling swift detection and response to potential security breaches.
*   **Containerization:** Efficient service deployment and management using **Docker** on Ubuntu, simplified via the **Portainer** web interface.
*   **Active Directory Emulation:** A realistic Active Directory environment for testing group policies, user access controls, and domain-based security attacks.

---
## Table of Contents - Step-by-Step Guides

| Component          | Description                                              | Guide                                                                    |
| ------------------ | -------------------------------------------------------- | ------------------------------------------------------------------------ |
| Proxmox Base Setup     | Guide for preparing Proxmox for the HomeLab          | [Proxmox Base Setup](configurations/Proxmox-Base-Setup.md)            |
| pfSense            | Configure pfSense for Network segmentation and firewall | [pfSense Configuration](configurations/pfsense-configuration.md)         |
| Kali Linux         | Setting up Kali Linux VM for Penetration testing        | [Kali Linux Setup](configurations/kali-linux-setup.md)                   |
| Ubuntu with Docker | Set up a containerized environment for application services | [Ubuntu Docker Setup](configurations/ubuntu-docker-setup.md)           |
| Docker Security Tools    | Deploying various security tools within Docker containers for enhanced vulnerability scanning, and threat analysis | [Docker-Security-Tools Setup](configurations/docker-security-tools-setup.md)|
| Wazuh              | Installing and configuring Wazuh HIDS, SEIM             | [Wazuh Installation](configurations/wazuh-installation.md)             |
| Wazuh Agent (Ubuntu)  | Deploying the Wazuh agent on Ubuntu-based systems   | [Wazuh-Agent-Ubuntu Setup](configurations/wazuh-agent-ubuntu-setup.md)   |
| Metasploitable 2 & DVWA | Setting up the vulnerable targets for ethical hacking  | [Metasploitable-DVWA Setup](configurations/metasploitable-dvwa-setup.md) |
| Windows AD         | Installing and configuring Active Directory services  | [Windows AD Setup](configurations/windows-ad-setup.md)              |
| Wazuh Agent (Windows) | Deploying the Wazuh agent on Windows-based systems | [Wazuh-Agent-Windows Setup](configurations/wazuh-agent-windows-setup.md) |
| Nessus             | Vulnerability scanning setup                          | [Nessus Setup](configurations/nessus-setup.md)                         |
| Security Onion     | Setting up network security monitoring                | [Security Onion Setup](configurations/security-onion-setup.md)         |
| TheHive & Cortex   | Incident response platform setup                      | [TheHive-Cortex Setup](configurations/thehive-cortex-setup.md)       |

---
## Next Steps

In the following sections, I will provide step-by-step instructions on how to replicate this home lab setup. This includes details on hardware requirements, software installation guides for each tool, networking configurations, and troubleshooting tips.  I'll also document common attack scenarios and defense strategies.

---

### Author

**Mahmud Mamme**

I am a cybersecurity enthusiast passionate about technology, security, and continuous learning. This home lab is an ongoing project that evolves as I explore new tools and security concepts.

For any inquiries or suggestions, feel free to reach out via [LinkedIn](https://www.linkedin.com/in/mahmudmamme/)  I'm always happy to connect.

---
