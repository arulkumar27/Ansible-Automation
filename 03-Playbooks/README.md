# Ansible Playbooks

This folder contains practical Ansible playbooks for automating common Linux server administration and configuration tasks.

The playbooks demonstrate how Ansible can be used to install packages, manage services, create users, manage files, configure web servers, and perform repeatable infrastructure automation.

## Playbooks Included

- Package Management
- Service Management
- User Management
- File Management
- Nginx Setup
- Apache Setup
- Docker Installation
- MySQL Installation
- System Updates
- Application Deployment
- Backup and Restore
- Server Health Checks

## Run a Playbook

```bash
ansible-playbook -i inventory.ini playbook-name.yml
```

## Run with Privilege Escalation

```bash
ansible-playbook -i inventory.ini playbook-name.yml --become
```

## Syntax Check

```bash
ansible-playbook playbook-name.yml --syntax-check
```

## Check Mode

```bash
ansible-playbook -i inventory.ini playbook-name.yml --check
```

## Check Mode with Differences

```bash
ansible-playbook -i inventory.ini playbook-name.yml --check --diff
```

These playbooks use Ansible built-in modules and follow idempotent automation practices.
