# Production Deployment Checklist

Before running playbooks in production, verify the following:

- Inventory is correct.
- Target hosts are reachable.
- Variables are validated.
- Secrets are encrypted using Ansible Vault.
- Playbook passes syntax check.
- Configuration files are validated.
- Required collections are installed.
- Backup is available.
- Maintenance window is confirmed.
- Rollback plan is ready.

---

## Validation Commands

Syntax Check

```bash
ansible-playbook site.yml --syntax-check
```

Dry Run

```bash
ansible-playbook site.yml --check
```

Inventory

```bash
ansible-inventory --graph
```

Connectivity

```bash
ansible all -m ping
```

These checks reduce deployment risk and improve reliability.
