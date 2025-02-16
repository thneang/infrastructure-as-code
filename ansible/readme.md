# Infrastructure as Code with Ansible - Nginx Reverse Proxy Setup

This project sets up a **reverse proxy** with **Nginx** and configures **SSL** using **Let's Encrypt** (Certbot) on a Debian server. It uses **Ansible** to automate the deployment and configuration.

## Prerequisites

Before running the Ansible playbook, ensure you have the following:

- A **Debian server** (or compatible) accessible via SSH.
- **Ansible** installed on your local machine. [Install Ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html).
- A domain name (e.g., `your-domain.com`), and the domain's DNS records should point to your server's IP address.
- If using SSL, an **email address** for the Let's Encrypt certificate registration.

## Project Overview

This project accomplishes the following tasks:

1. Installs and configures **Nginx** as a reverse proxy.
2. Configures **Let's Encrypt** (Certbot) for SSL certificates.
3. Automatically redirects HTTP traffic to HTTPS.
4. Ensures that **Nginx** is enabled and started.
5. Sets up a cron job for **automatic certificate renewal**.

## How to Use

### 1. Clone this repository

```bash
git clone https://github.com/yourusername/your-repository.git
cd your-repository

### 2. Configure your inventory
'domain' and 'email' are the 2 mandatory vars needed

### 3. Execute the play
ansible-playbook -i inventories/main.yml playbooks/file.yml