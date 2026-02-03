# Ansible GCP Deployment Showcase

This repository demonstrates the automation of web application deployment on Google Cloud Platform (GCP) Virtual Machines using Ansible. It covers automated Docker installation, Nginx configuration, and application containerization.

## Project Overview

### Key Features
- Automated Infrastructure Configuration: One-click setup for GCP Debian instances.
- Docker Integration: Automated installation of Docker Engine and Docker Compose.
- Microservices Deployment: Deployment of containerized web applications using Docker Compose.
- Custom Nginx Setup: Installation and configuration of Nginx as a web server with a custom landing page.

### Technical Workflow
When executed, the Ansible playbooks perform the following actions:
1. Establish SSH connections to target GCP instances.
2. Install necessary system dependencies (Docker, Nginx).
3. Transfer application configurations and static files to the remote server.
4. Initialize the application services, making them accessible via public endpoints.

---

## Project Structure

```text
.
├── ansible.cfg             # Ansible configuration file
├── deploy_docker_app.yml     # Playbook for Docker and application deployment
├── install_nginx.yml        # Playbook for Nginx installation
├── inventory.ini.example    # Template for server inventory configuration
├── files/                   # Static files and configurations
│   ├── docker-compose.yml   # Docker Compose service definitions
│   └── index.html           # Custom application landing page
└── .gitignore               # Git exclusion rules for sensitive data
```

---

## Getting Started

### 1. Prerequisites
- Ansible installed on the local management machine.
- Access to one or more GCP Virtual Machines (Debian 12 recommended).
- SSH key-based authentication configured for the target VMs.

### 2. Configuration
Copy the inventory template and populate it with your specific server details:
```bash
cp inventory.ini.example inventory.ini
# Edit inventory.ini to include your VM IP addresses and SSH user
```

### 3. Execution

#### Install and Configure Nginx:
```bash
ansible-playbook install_nginx.yml
```

#### Deploy Docker Application:
```bash
ansible-playbook deploy_docker_app.yml
```

---

## Security and Best Practices
- Inventory Data Protection: The `inventory.ini` file is explicitly excluded from version control to prevent unauthorized exposure of server IP addresses.
- Credential Management: SSH keys and sensitive configuration files are managed outside the repository scope.
- State Isolation: Infrastructure state files (such as Terraform .tfstate) are excluded to maintain environment integrity.
- Modular Design: Playbooks are structured by function to ensure maintainability and reusability.

---

Maintainer: [Your Name/GitHub Handle]
