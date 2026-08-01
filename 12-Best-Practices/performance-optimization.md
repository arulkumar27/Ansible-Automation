# Performance Optimization

## Gather Facts Only When Needed

Disable fact gathering for simple tasks.

```yaml
gather_facts: false
```

---

## Use Handlers

Restart services only after changes occur.

---

## Use Loops

Avoid duplicate tasks.

Preferred:

```yaml
loop:
  - nginx
  - docker
  - git
```

---

## Minimize Shell Commands

Use built-in modules whenever possible.

---

## Use Dynamic Inventory

Avoid manually updating inventory files in cloud environments.

---

## Execute Tasks in Parallel

Increase the number of forks.

Example:

```ini
forks = 20
```

---

## Use Tags

Execute only required tasks.

```bash
ansible-playbook site.yml --tags nginx
```
