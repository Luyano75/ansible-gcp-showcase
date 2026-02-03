# 🚀 Ansible GCP Deployment Showcase

This repository demonstrates how to automate the deployment of web applications on Google Cloud Platform (GCP) Virtual Machines using **Ansible**. It features automated Docker installation, Nginx configuration, and application containerization.

## 🌟 Showcase

### 🛠️ Key Features
- **Automated Infrastructure Configuration**: One-click setup for GCP Debian instances.
- **Docker Integration**: Automates the installation of Docker Engine and Docker Compose.
- **Microservices Deployment**: Deploys a containerized web application using Docker Compose.
- **Custom Nginx Setup**: Installs and configures Nginx as a web server with a custom landing page.

### 📸 Preview
When you run the playbooks, Ansible will:
1. Connect via SSH to your GCP instances.
2. Install all necessary dependencies (Docker, Nginx).
3. Push your application files to the remote server.
4. Launch the application, making it accessible via the VM's public IP.

---

## 📂 Project Structure

```text
.
├── ansible.cfg             # Ansible configuration file
├── deploy_docker_app.yml     # Playbook for Docker & App deployment
├── install_nginx.yml        # Playbook for Nginx installation
├── inventory.ini.example    # Template for your server inventory
├── files/                   # Static files and configurations
│   ├── docker-compose.yml   # Multi-container definition
│   └── index.html           # Custom landing page
└── .gitignore               # Securely excludes sensitive files
```

---

## 🚀 Getting Started

### 1. Prerequisites
- Ansible installed on your local machine.
- One or more GCP VMs (Debian 12/Bookworm recommended).
- SSH access to your VMs.

### 2. Configuration
Copy the inventory template and fill in your VM details:
```bash
cp inventory.ini.example inventory.ini
# Edit inventory.ini with your IPs and username
```

### 3. Usage

#### To setup Nginx:
```bash
ansible-playbook install_nginx.yml
```

#### To deploy the Docker application:
```bash
ansible-playbook deploy_docker_app.yml
```

---

## 🛡️ Security & Best Practices
- **Inventory Protection**: The `inventory.ini` file is ignored by Git to prevent leaking private IP addresses.
- **State Management**: Infrastructure state files (`.tfstate`) are excluded.
- **Modular Playbooks**: Tasks are separated for better maintainability.

---

Made with ❤️ by [Your Name/GitHub Handle]
