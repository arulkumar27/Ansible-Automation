# YAML Style Guide

Follow a consistent YAML style for readability.

## Use Two-Space Indentation

```yaml
tasks:
  - name: Install Nginx
    ansible.builtin.package:
      name: nginx
      state: present
```

---

## Use Fully Qualified Collection Names

Preferred:

```yaml
ansible.builtin.package
```

instead of:

```yaml
package
```

---

## Quote File Modes

Good:

```yaml
mode: "0644"
```

---

## Use Lowercase File Names

Good:

```
install-nginx.yml
```

Bad:

```
InstallNginx.yml
```

---

## Keep Tasks Short

Each task should perform one responsibility.

Avoid combining multiple operations into a single task.

---

## Use Blank Lines Sparingly

Group related tasks logically while avoiding excessive spacing.

Consistent formatting improves readability and maintainability.
