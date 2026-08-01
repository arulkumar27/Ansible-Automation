# Ansible Role Best Practices

## Keep Roles Small

Each role should perform **one responsibility only**.

Examples:

- common
- nginx
- docker
- mysql
- users

---

## Make Roles Reusable

Avoid hardcoding values.

Use variables instead.

Example:

```yaml
name: "{{ package_name }}"
```

---

## Use Defaults

Store configurable values inside:

```
defaults/main.yml
```

---

## Keep Tasks Modular

Split large playbooks into reusable roles.

Instead of:

- 500-line playbook

Prefer:

- common role
- nginx role
- docker role
- mysql role

---

## Use Handlers

Restart services only when changes occur.

```yaml
notify: Restart Nginx
```

---

## Prefer Built-in Modules

Use:

- package
- service
- file
- template
- copy

instead of shell commands whenever possible.

---

## Write Idempotent Tasks

Running the same role multiple times should not create unnecessary changes.

---

## Follow Naming Standards

Good examples:

- common
- nginx
- docker
- mysql

Avoid generic names like:

- role1
- test
- demo

---

## Document Your Roles

Every role should contain a README explaining:

- Purpose
- Variables
- Requirements
- Usage
