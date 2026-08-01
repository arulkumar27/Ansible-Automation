# Prerequisites

Before executing the playbook, ensure the following requirements are met.

## Control Node

- Linux or macOS
- Ansible installed
- Python 3
- SSH client

---

## Managed Servers

- Ubuntu 22.04 or later
- Python installed
- SSH enabled
- User with sudo privileges

---

## Authentication

Configure SSH key-based authentication.

Example:

```bash
ssh-copy-id ubuntu@192.168.1.10
```

---

## Verify Connectivity

```bash
ansible all -i inventory.ini -m ping
```

Expected Output

```
SUCCESS
```
