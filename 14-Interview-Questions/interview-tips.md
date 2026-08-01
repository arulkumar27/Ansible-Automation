# Interview Tips

## Before the Interview

- Review Linux basics.
- Practice Ansible commands.
- Understand YAML syntax.
- Revise your projects.
- Review troubleshooting scenarios.

---

## During the Interview

- Explain concepts clearly.
- Mention real-world examples.
- Explain why you use a module.
- Highlight best practices.
- Speak confidently and logically.

---

## Common Mistakes

- Confusing Playbooks and Roles.
- Using `shell` unnecessarily.
- Forgetting handlers.
- Hardcoding secrets.
- Ignoring idempotency.

---

## Commands to Remember

```bash
ansible all -m ping
```

```bash
ansible-playbook site.yml
```

```bash
ansible-playbook site.yml --check
```

```bash
ansible-playbook site.yml --syntax-check
```

```bash
ansible-inventory --graph
```

```bash
ansible-vault create secrets.yml
```

---

## Final Advice

- Focus on understanding rather than memorizing.
- Explain your own projects with confidence.
- Be prepared to troubleshoot real-world scenarios.
