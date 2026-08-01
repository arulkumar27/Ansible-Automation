# Idempotency

## What is Idempotency?

Idempotency means a playbook can be executed multiple times and the final system state remains the same.

If nothing has changed, Ansible should report:

```
ok
```

instead of:

```
changed
```

---

## Good Example

```yaml
- name: Install Nginx
  ansible.builtin.package:
    name: nginx
    state: present
```

If Nginx is already installed, Ansible makes no changes.

---

## Bad Example

```yaml
- name: Install Nginx
  ansible.builtin.shell: apt install nginx -y
```

The shell command always executes and cannot reliably determine whether a change occurred.

---

## Best Practices

- Prefer Ansible modules over shell commands.
- Use `state: present`, `started`, or `absent`.
- Use `changed_when: false` for read-only commands.
- Use handlers instead of restarting services in every task.
