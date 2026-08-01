# Linux Server Bootstrap using Ansible

## Project Overview

This project automates the initial configuration of newly provisioned Linux servers using Ansible.

Instead of manually configuring every server, the playbook performs all required setup tasks automatically, ensuring every server follows the same standards.

This project represents a real-world infrastructure provisioning workflow used by DevOps and Cloud Engineering teams.

---

## Objectives

- Configure Linux servers automatically
- Reduce manual configuration
- Improve consistency
- Secure server configuration
- Prepare servers for application deployment

---

## Features

- System update
- Package installation
- User and group creation
- SSH hardening
- Timezone configuration
- Hostname configuration
- Firewall configuration
- Service management
- Health verification

---

## Technologies

- Ansible
- Ubuntu Linux
- OpenSSH
- UFW Firewall
- Jinja2 Templates
- YAML

---

## Project Structure

```text
linux-server-bootstrap/
│
├── inventory.ini
├── ansible.cfg
├── bootstrap.yml
├── group_vars/
├── host_vars/
├── templates/
├── files/
└── screenshots/
```

---

## Execute

```bash
ansible-playbook -i inventory.ini bootstrap.yml
```

---

## Outcome

After execution, the server is fully configured and ready for application deployment.
