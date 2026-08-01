# Module Best Practices

Ansible provides hundreds of built-in modules. Prefer these modules over shell or command whenever possible.

## Use Built-in Modules

Preferred:

```yaml
- name: Install Nginx
  ansible.builtin.package:
    name: nginx
    state: present
```

Avoid:

```yaml
- name: Install Nginx
  ansible.builtin.shell: apt install nginx -y
```

---

## Use the Correct Module

| Task | Recommended Module |
|------|---------------------|
| Install Packages | package / apt / dnf |
| Manage Services | service |
| Copy Files | copy |
| Dynamic Files | template |
| Create Users | user |
| Create Directories | file |
| Download Files | get_url |
| Execute Commands | command |
| Complex Shell Operations | shell |

---

## Avoid Shell When Possible

Use `shell` only when no suitable module exists.

---

## Benefits

- Idempotent
- More reliable
- Better error handling
- Easier maintenance
