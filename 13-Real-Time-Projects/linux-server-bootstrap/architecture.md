# Architecture

```text
                    Git Repository
                           │
                           ▼
                  Ansible Control Node
                           │
                 SSH Key Authentication
                           │
         ┌─────────────────┴─────────────────┐
         │                                   │
         ▼                                   ▼
   Ubuntu Server 01                   Ubuntu Server 02
         │                                   │
         ▼                                   ▼
   Bootstrap Playbook                 Bootstrap Playbook
         │                                   │
         ▼                                   ▼
 Packages Installed             Users Configured
 SSH Hardened                   Firewall Enabled
 Services Started               Health Verified
```

---

## Components

### Control Node

Runs Ansible playbooks.

---

### Managed Nodes

Linux servers configured remotely.

---

### Inventory

Stores server details.

---

### Playbook

Contains automation tasks.

---

### SSH

Used for secure communication.

---

### Result

Every server is configured consistently without manual intervention.
