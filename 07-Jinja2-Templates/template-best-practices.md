# Jinja2 Template Best Practices

## Use Variables Instead of Hardcoding

❌ Avoid

```text
server_name example.com;
```

✅ Prefer

```jinja
server_name {{ server_name }};
```

---

## Keep Business Logic Out of Templates

Templates should focus on rendering configuration, not implementing complex logic.

---

## Use Meaningful Variable Names

Good examples:

- application_name
- environment
- server_name
- document_root
- backend_servers

---

## Keep Templates Reusable

A single template should work for:

- Development
- Testing
- Staging
- Production

by changing only variable values.

---

## Validate Configuration

Whenever possible, validate generated configuration files before restarting services.

Example:

```bash
nginx -t
```

---

## Store Templates in a Dedicated Directory

```
templates/
```

This follows the standard Ansible project structure.

---

## Prefer the Template Module

Use:

```yaml
ansible.builtin.template
```

instead of `copy` when the file contains variables or dynamic content.

---

## Trigger Handlers Only When Needed

Use:

```yaml
notify: Restart Nginx
```

so services restart only when the rendered template changes.

---

## Follow Idempotent Practices

Running the playbook multiple times without changes should result in **no changes** and should not restart services unnecessarily.
