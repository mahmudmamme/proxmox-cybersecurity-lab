# Ubuntu Server VM Configuration for Docker and Portainer (Overview)

This guide provides an overview of the steps required to set up an Ubuntu Server VM in Proxmox for running Docker and Portainer. 

## 1. Proxmox VM Setup

*   Create a new Ubuntu Server VM in Proxmox, specifying:
    *   VM ID and Name (e.g., `prod-docker`, VM ID `203`)
    *   Ubuntu Server ISO as the boot medium
    *   Sufficient disk space (e.g., 160 GB)
    *   Adequate RAM (e.g., 16 GB)
    *   Network connection to the lab network (e.g., `vmbr2` with VLAN 30, if applicable)

## 2. Ubuntu Server Installation

*   Start the VM and follow the Ubuntu Server installer.
*   Enable OpenSSH Server during installation for remote access.
*   Verify the VM receives an IP address from the DHCP server.

## 3. Docker Installation

*   Install Docker using the official Docker installation guide for Ubuntu: [https://docs.docker.com/engine/install/ubuntu/](https://docs.docker.com/engine/install/ubuntu/)
*   Ensure the Docker service is running and enabled after installation: `sudo systemctl start docker` and `sudo systemctl enable docker`.

## 4. Portainer Installation

*   Create a Docker volume for Portainer data: `sudo docker volume create portainer_data`
*   Deploy the Portainer container using the following command:

    ```bash
    sudo docker run -d -p 8000:8000 -p 9443:9443 --name portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer-ce:2.21.5
    ```

## 5. Access Portainer

*   Access the Portainer web UI at `http://<UbuntuServerIP>:9000` or `https://<UbuntuServerIP>:9443`.
*   Create an admin user and connect to the local Docker environment.

**Key Considerations:**

*   The firewall must be configured to allow access to Portainer on ports 9000 and 9443 (if needed).
*   Docker and Portainer should be kept updated with the latest security patches.
