# Handler Best Practices

## Use Handlers Only for Change-Driven Tasks

Use handlers for operations that should occur only after a configuration change.

Examples:

- Restart Services
- Reload Services
- Reload Systemd
- Restart Docker
- Restart Database Services

---

## Use `notify`

Trigger handlers using the `notify` keyword.

```yaml
notify: Restart Nginx
```

---

## Avoid Duplicate Restarts

If multiple tasks notify the same handler, Ansible executes the handler **only once** at the end of the play.

---

## Use `listen` for Shared Actions

Multiple handlers can listen to the same notification.

```yaml
listen: Restart Web Services
```

This is useful when multiple services need to restart together.

---

## Use `flush_handlers` Carefully

By default, handlers run at the end of a play.

Use:

```yaml
- meta: flush_handlers
```

only when a service must restart before subsequent tasks continue.

---

## Keep Handlers Focused

A handler should perform one clear action.

Good examples:

- Restart Nginx
- Reload Apache
- Restart Docker
- Reload Systemd

Avoid combining unrelated operations in a single handler.

---

## Prefer Built-in Modules

Use modules such as:

- ansible.builtin.service
- ansible.builtin.systemd

instead of raw shell commands whenever possible.

---

## Follow Idempotent Practices

Handlers should execute only when notified after a task reports a change.

This minimizes unnecessary service interruptions and supports reliable, repeatable automation.
