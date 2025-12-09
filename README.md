# Ansible Django Deploy

This project provides an automated way to deploy a Django application using Ansible.  
It handles common deployment tasks such as installing dependencies, setting up the environment, pulling the application code, applying database migrations, collecting static files, and restarting the service.

The goal of this project is to demonstrate Infrastructure as Code (IaC), configuration management and repeatable deployments — essential practices in DevOps, NOC and IT Operations workflows.

---

## Requirements

Ensure the target server has the following installed:

- Python 3.x  
- Ansible  
- Git  

---

## How to Use

### 1. Clone the repository

```
git clone https://github.com/leovoltz/ansible-django-deploy.git
```

### 2. Navigate into the project directory

```
cd ansible-django-deploy
```

### 3. Configure your inventory file

Edit `inventory.ini` and add your server details:

```
[servers]
server ansible_host=YOUR_SERVER_IP ansible_user=YOUR_USER ansible_ssh_private_key_file=PATH_TO_PRIVATE_KEY
```

### 4. Adjust variables

Update the file `vars.yml` with your Django project configuration, repository URL, environment variables and paths.

### 5. Run the playbook

```
ansible-playbook -i inventory.ini deploy.yml
```

---

## What This Playbook Does

When executed, the playbook performs the following automated steps:

- Updates the operating system  
- Installs system dependencies (Python, pip, virtualenv, supervisor, etc.)  
- Configures environment variables  
- Clones or updates your Django reposit
