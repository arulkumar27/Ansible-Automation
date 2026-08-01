# Ansible Roles

Ansible Roles provide a structured and reusable way to organize automation content.

Instead of keeping all tasks, variables, handlers, templates, and files inside one large playbook, roles separate them into logical components.

This folder contains simplified examples that demonstrate how roles are created, organized, and called from playbooks.

## Topics Covered

- Role structure
- Reusable automation
- Role-based playbooks
- Common role
- Nginx role
- Docker role
- MySQL role
- Role best practices
- Real-time role usage

## Why Roles Are Used

Roles help to:

- Organize large playbooks
- Reuse automation logic
- Separate tasks by responsibility
- Improve readability
- Simplify maintenance
- Support team collaboration

## Example

```yaml
---
- name: Configure Web Servers
  hosts: webservers
  become: true

  roles:
    - common
    - nginx
