# Recommended Project Structure

A well-organized project is easier to maintain and understand.

```text
ansible-project/
│
├── inventories/
├── playbooks/
├── roles/
├── group_vars/
├── host_vars/
├── templates/
├── files/
├── README.md
└── ansible.cfg
```

## Why This Structure?

- Separates configuration from logic
- Encourages role reuse
- Simplifies collaboration
- Easier troubleshooting
- Scales to larger projects

## Recommendation

Keep playbooks small and reusable.

Move repeated logic into roles.
