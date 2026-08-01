# Ansible Roles Interview Questions

## 1. What is a Role?

A Role is a reusable collection of tasks, variables, handlers, templates, and files organized into a standard directory structure.

---

## 2. Why do we use Roles?

- Reusability
- Better organization
- Easier maintenance
- Team collaboration

---

## 3. Standard Role Structure?

- tasks
- handlers
- defaults
- vars
- files
- templates
- meta

---

## 4. Difference between defaults and vars?

- **defaults** → Lowest variable precedence
- **vars** → Higher precedence and role-specific values

---

## 5. What is Ansible Galaxy?

A repository used to download and share Ansible Roles and Collections.

---

## 6. Install a Role.

```bash
ansible-galaxy install geerlingguy.nginx
```

---

## 7. Create a Role.

```bash
ansible-galaxy role init nginx
```

---

## 8. Can Roles depend on other Roles?

Yes.

Dependencies are defined in:

```
meta/main.yml
```

---

## 9. Can multiple Roles run in one Playbook?

Yes.

Example:

```yaml
roles:
  - common
  - nginx
  - docker
```

---

## 10. Best Practice?

Keep one responsibility per role.
