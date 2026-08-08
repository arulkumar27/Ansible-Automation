# Multi-Server Configuration with Ansible Roles

This project demonstrates how Ansible Roles can be used to automate configuration across multiple Linux servers.

The automation configures common Linux settings, deploys Nginx on web servers, installs Docker, deploys a Python Flask application as a systemd service, and enables basic server monitoring.

---

## Architecture

The environment contains:

* 1 Ansible Control Node
* 2 Web Servers
* 1 Application Server

```text
                    Ansible Control Node
                           |
                           |
            --------------------------------
            |               |              |
            |               |              |
          web1             web2            app1
            |               |              |
       Nginx + Docker  Nginx + Docker   Flask + Docker
            |               |              |
       Monitoring      Monitoring       Monitoring
```

---

## Roles Used

### Common Role

Applied to all managed servers.

Responsibilities:

* Update package cache
* Install common Linux utilities
* Create DevOps user
* Configure required directories
* Maintain common server configuration

### Nginx Role

Applied only to web servers.

Responsibilities:

* Install Nginx
* Start and enable Nginx
* Deploy HTML content using Jinja2
* Use handlers to restart Nginx when configuration changes

### Docker Role

Applied to web and application servers.

Responsibilities:

* Install Docker
* Start Docker service
* Enable Docker during boot
* Add required users to Docker group
* Verify Docker installation

### Application Role

Applied only to the application server.

Responsibilities:

* Install Python and Flask
* Create application directory
* Deploy Flask application
* Generate application files using Jinja2
* Create systemd service
* Start and enable application service
* Restart application when configuration changes

### Monitoring Role

Applied to all servers.

Responsibilities:

* Install monitoring utilities
* Install `sysstat`
* Enable system statistics collection
* Start and enable monitoring services

---

## Technologies Used

* Ansible
* Ubuntu Linux
* YAML
* Jinja2
* Nginx
* Docker
* Python
* Flask
* systemd
* sysstat
* htop
* AWS EC2

---

## Project Structure

```text
multi-server-configuration-with-ansible-roles/
├── README.md
├── .gitignore
├── ansible.cfg
├── inventory.ini.example
├── site.yml
├── group_vars/
│   └── all.yml
└── roles/
    ├── common/
    │   └── tasks/
    │       └── main.yml
    │
    ├── nginx/
    │   ├── tasks/
    │   │   └── main.yml
    │   ├── handlers/
    │   │   └── main.yml
    │   └── templates/
    │       └── index.html.j2
    │
    ├── docker/
    │   └── tasks/
    │       └── main.yml
    │
    ├── app/
    │   ├── defaults/
    │   │   └── main.yml
    │   ├── tasks/
    │   │   └── main.yml
    │   ├── handlers/
    │   │   └── main.yml
    │   └── templates/
    │       ├── app.py.j2
    │       └── app.service.j2
    │
    └── monitoring/
        ├── tasks/
        │   └── main.yml
        └── handlers/
            └── main.yml
```

---

# Prerequisites

Before running this project, prepare the following infrastructure.

## Ansible Controller

Requirements:

* Ubuntu Linux
* Ansible installed
* SSH access to managed nodes
* Python installed

Check Ansible:

```bash
ansible --version
```

## Managed Nodes

Create:

* 2 Ubuntu web servers
* 1 Ubuntu application server

Python should be available on the managed nodes.

Verify:

```bash
python3 --version
```

---

# Step 1 - Install Ansible

On the Ansible Control Node:

```bash
sudo apt update
sudo apt install ansible -y
```

Verify:

```bash
ansible --version
```

---

# Step 2 - Clone the Repository

```bash
git clone https://github.com/arulkumar27/Ansible-Automation.git
```

Move into the project directory:

```bash
cd Ansible-Automation/13-Real-Time-Projects/multi-server-configuration-with-ansible-roles
```

---

# Step 3 - Prepare SSH Authentication

The Ansible Control Node must be able to connect to all managed servers through SSH.

Store the OpenSSH-compatible private key securely on the controller.

Example:

```bash
chmod 400 /home/ubuntu/private-key.pem
```

Test SSH manually:

```bash
ssh -i /home/ubuntu/private-key.pem ubuntu@<MANAGED_NODE_IP>
```

SSH connectivity should work before running Ansible.

---

# Step 4 - Create Inventory

Copy the example inventory:

```bash
cp inventory.ini.example inventory.ini
```

Edit:

```bash
nano inventory.ini
```

Example:

```ini
[webservers]
web1 ansible_host=<WEB1_PRIVATE_IP>
web2 ansible_host=<WEB2_PRIVATE_IP>

[appservers]
app1 ansible_host=<APP1_PRIVATE_IP>

[all:vars]
ansible_user=ubuntu
ansible_ssh_private_key_file=/home/ubuntu/private-key.pem
```

Do not commit the real `inventory.ini` file because it may contain infrastructure information and private-key paths.

---

# Step 5 - Test Inventory

Display all configured hosts:

```bash
ansible all --list-hosts
```

Expected:

```text
hosts (3):
  web1
  web2
  app1
```

Check web servers:

```bash
ansible webservers --list-hosts
```

Check application servers:

```bash
ansible appservers --list-hosts
```

---

# Step 6 - Test Ansible Connectivity

Run:

```bash
ansible all -m ping
```

Expected:

```text
web1 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}

web2 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}

app1 | SUCCESS => {
    "changed": false,
    "ping": "pong"
}
```

If this fails, verify:

* SSH connectivity
* Security groups
* Private-key permissions
* Correct SSH username
* Correct private IP addresses

---

# Step 7 - Test Privilege Escalation

The roles require sudo privileges.

Run:

```bash
ansible all -b -m command -a "whoami"
```

Expected:

```text
root
```

for all managed servers.

---

# Step 8 - Configure Variables

Project-wide variables are stored in:

```text
group_vars/all.yml
```

Example:

```yaml
---
admin_user: devops

app_name: demoapp
app_port: 5000
app_directory: "/opt/{{ app_name }}"

docker_users:
  - ubuntu
  - devops
```

Role defaults are stored separately under:

```text
roles/app/defaults/main.yml
```

This allows values to be overridden without changing the role logic.

---

# Step 9 - Validate the Main Playbook

Before executing automation, check YAML and Ansible syntax:

```bash
ansible-playbook site.yml --syntax-check
```

Expected:

```text
playbook: site.yml
```

---

# Step 10 - Run the Playbook

Execute:

```bash
ansible-playbook site.yml
```

The playbook applies the following configuration:

```text
All Servers
  ├── common
  └── monitoring

Web Servers
  ├── nginx
  └── docker

Application Server
  ├── docker
  └── app
```

---

# Step 11 - Verify Nginx

Check Nginx service:

```bash
ansible webservers -b -m command -a "systemctl is-active nginx"
```

Expected:

```text
active
```

Test web1:

```bash
curl http://<WEB1_PRIVATE_IP>
```

Test web2:

```bash
curl http://<WEB2_PRIVATE_IP>
```

The page displays information generated using Ansible facts such as:

* Hostname
* Operating system

---

# Step 12 - Verify Docker

Run:

```bash
ansible all -b -m command -a "docker --version"
```

Check Docker service:

```bash
ansible all -b -m command -a "systemctl is-active docker"
```

Expected:

```text
active
```

---

# Step 13 - Verify Flask Application

Check application service:

```bash
ansible appservers -b -m command -a "systemctl is-active demoapp"
```

Expected:

```text
active
```

Check listening port:

```bash
ansible appservers -b -m shell -a "ss -lntp | grep 5000"
```

Expected:

```text
0.0.0.0:5000
```

Test application:

```bash
curl http://<APP_SERVER_PRIVATE_IP>:5000
```

Test health endpoint:

```bash
curl http://<APP_SERVER_PRIVATE_IP>:5000/health
```

Expected:

```json
{"status":"UP"}
```

---

# Step 14 - Verify Monitoring

Check sysstat:

```bash
ansible all -b -m command -a "systemctl is-active sysstat"
```

Expected:

```text
active
```

Check system statistics:

```bash
ansible all -b -m command -a "sar -V"
```

---

# Step 15 - Test Idempotency

Run the playbook again:

```bash
ansible-playbook site.yml
```

Most tasks should now show:

```text
ok
```

instead of:

```text
changed
```

This demonstrates Ansible idempotency.

Ansible keeps the managed servers in the desired state without unnecessarily repeating configuration changes.

---

# Ansible Workflow

```text
Inventory
   │
   ▼
site.yml
   │
   ├── common
   ├── monitoring
   ├── nginx
   ├── docker
   └── app
       │
       ▼
Tasks
   │
   ├── Packages
   ├── Users
   ├── Templates
   ├── Services
   └── Application Deployment
       │
       ▼
Managed Servers
```

---

# Role Workflow

Example Nginx deployment:

```text
site.yml
   │
   ▼
nginx role
   │
   ▼
tasks/main.yml
   │
   ├── Install Nginx
   ├── Deploy Template
   └── Start Service
            │
            ▼
          notify
            │
            ▼
handlers/main.yml
            │
            ▼
       Restart Nginx
```

---

# Jinja2 Template Usage

Jinja2 templates are used to generate dynamic configuration and application files.

Example:

```jinja2
{{ ansible_hostname }}
{{ ansible_distribution }}
{{ app_name }}
{{ app_port }}
```

Ansible replaces these values during playbook execution.

---

# Variables and Defaults

The project separates configuration values from task logic.

Example:

```text
roles/app/defaults/main.yml
        │
        ▼
Default Values
        │
        ▼
group_vars/all.yml
        │
        ▼
Project Override
        │
        ▼
Jinja2 Template
```

This makes roles reusable across different environments.

---

# Handlers

Handlers are triggered only when required.

Example:

```yaml
notify: Restart nginx
```

The restart happens only when the related configuration changes.

This avoids unnecessary service restarts.

---

# Troubleshooting

## Ansible Ping Fails

Verify SSH manually:

```bash
ssh -i /home/ubuntu/private-key.pem ubuntu@<SERVER_IP>
```

Check private key permissions:

```bash
chmod 400 /home/ubuntu/private-key.pem
```

---

## Permission Denied

Verify:

```ini
ansible_user=ubuntu
```

and confirm the correct private key is being used.

---

## Ansible Facts Undefined

Variables such as:

```text
ansible_hostname
ansible_distribution
ansible_default_ipv4
```

require fact gathering.

Use a normal playbook with:

```yaml
gather_facts: true
```

or leave it unspecified because fact gathering is enabled by default.

---

## Flask Application Not Reachable

Check service:

```bash
systemctl status demoapp
```

Check port:

```bash
ss -lntp | grep 5000
```

Test locally:

```bash
curl http://127.0.0.1:5000
```

If the application works locally but not remotely, verify the network and security-group configuration.

---

## Nginx Not Running

Check:

```bash
systemctl status nginx
```

Verify configuration:

```bash
nginx -t
```

---

# Security Notes

Do not commit sensitive files such as:

```text
*.pem
*.ppk
inventory.ini
.vault_pass
```

Use:

```gitignore
*.pem
*.ppk
inventory.ini
*.retry
.vault_pass
```

Only `inventory.ini.example` should be stored in the repository.

---

# Concepts Practiced

This project provides hands-on practice with:

* Ansible Control Node
* Managed Nodes
* Static Inventory
* Inventory Groups
* Playbooks
* Ansible Roles
* Tasks
* Handlers
* Jinja2 Templates
* Variables
* Role Defaults
* `group_vars`
* Ansible Facts
* Package Management
* User Management
* File Management
* Service Management
* systemd
* Privilege Escalation
* Application Deployment
* Configuration Management
* Multi-Server Automation
* Idempotency
* Troubleshooting

---

# Result

After successful execution:

* Common Linux configuration is applied to all servers
* Nginx is deployed on both web servers
* Docker is installed and enabled
* Flask application is deployed on the application server
* Application is managed using systemd
* Monitoring utilities are configured
* Configuration is organized using reusable Ansible Roles
* The complete environment can be managed from a single Ansible Control Node

---

## Project Summary

This project demonstrates a practical multi-server Ansible workflow where a central control node manages different server responsibilities through reusable roles.

It shows how configuration management, application deployment, service management, templates, variables, handlers, and idempotency can be combined into a structured infrastructure automation workflow.
